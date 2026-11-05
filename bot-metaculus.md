# Le bot Metaculus, ou le fondement empirique

### Ce que le dispositif à trois bras mesure, et ce qu'il n'a pas encore mesuré

**Document d'analyse · version 0.7.51 · révision 1 · 5 novembre 2026**

Dépôt du bot : `Othman-Benbrahim/metac-bot-template` · version **0.5.1** · skill embarqué **0.7.51**
Dépôt analysé : `Othman-Benbrahim/alphabet-situationnel` · version 0.7.51 · licence MIT
Registre lu au 5 novembre 2026 : 11 lignes binaires scellées, 3 questions distinctes, **0 question résolue**

> **Pourquoi ce document existe.** Les quatre autres documents de ce dépôt décrivent le protocole sur
> pièces : ce qu'il promet, ce qu'il calcule, ce qu'il faudrait pour le prendre en défaut. Celui-ci
> décrit la seule pièce du dispositif qui produise des **épisodes prospectifs** — des prévisions
> scellées avant l'issue, sur des questions posées par un tiers. C'est le chaînon que la note
> appelait « le mur », et il existe désormais. Il ne l'a pas encore franchi.
>
> **Ce que ce document n'est pas.** Ce n'est pas une validation du bot, ni un relevé de performance :
> aucune question du registre n'est résolue à la date de cette note, donc aucun score n'existe. Les
> chiffres cités sont des **comptes de lignes et de champs**, pas des résultats prédictifs — sauf
> mention contraire, et la mention est alors un chiffre du skill, pas du bot.

> **Versionnement.** La version de ce document suit celle du skill embarqué par le bot, elle-même
> alignée sur le dépôt analysé ; la révision compte les réécritures à version constante. Voir
> `README.md` et `CHANGELOG.md`. Aucun document ne cite le commit qui le contient.

---

## 1 · Ce qu'est le bot

Le bot est un **fork de `Metaculus/metac-bot-template`**, le modèle public de bot de tournoi : le
harnais d'appel à l'API, les workflows GitHub Actions et la structure de dépôt viennent de ce modèle ;
les fichiers propres à l'Alphabet (`alphabet_*.py`, `score_registre.py`, `tests/`, workflows
`*alphabet*`) sont sous licence MIT, le reste du dépôt restant sous ses propres conditions.

Il tourne **toutes les vingt minutes** dans GitHub Actions, regarde si le tournoi FutureEval a publié
des questions nouvelles — elles ne restent ouvertes que trois heures, à heure aléatoire — et en traite
**cinq au plus par jour** (`ALPHABET_MAX_QUESTIONS`), le compte étant tenu dans
`registre/passages.jsonl` **avant** toute prévision. Un contrôle sans question nouvelle n'écrit rien et
ne coûte rien. Un lancement manuel a son propre plafond, hors quota quotidien ; le mode
`test_questions` (zone de test de Metaculus) est enregistré comme essai et n'entre pas dans le score.

Le dépôt porte une copie exacte du skill dans `alphabet-situationnel/`, contrôlée par
`moteur.py audit` **avant chaque passage** : le bot ne peut pas tourner sur une copie modifiée du
skill sans que l'audit le refuse. C'est la garantie que le chiffre posté sort bien du moteur publié.

**La question de fond, et elle est unique.** Une lecture structurelle de la situation — le skill —
améliore-t-elle un simple taux de base ? Tout le dispositif est construit pour rendre cette question
tranchable, y compris contre lui-même.

---

## 2 · Les trois bras

| Bras | Ce qui produit la probabilité | Ce qu'il représente |
|---|---|---|
| **A** | le modèle de langage seul, comme le bot modèle de Metaculus | le témoin : ce qu'on obtient **sans** le skill |
| **B** | une classe de référence : « sur des situations comparables, combien de fois l'événement s'est produit » | le taux de base, avec sa source et sa date |
| **C** | le skill : lecture de la situation, puis calcul par le moteur, à partir de B | ce que la lecture ajoute à B |

A est calculé et scellé **avant toute lecture** : il ne peut pas être influencé par B ou C. C'est la
première propriété qui rend le dispositif interprétable — sans elle, un bras « modèle seul » calculé
après la lecture ne serait qu'un second avis informé.

Les trois probabilités sont **scellées** (SHA-256) dans une ligne de registre avant l'échéance, avec le
dossier de lecture complet. L'historique Git date chaque écriture. C'est ce qui distingue un registre
d'un cahier : une ligne scellée ne se réécrit pas après l'issue.

**Ce que C−B mesure, et ce que A mesure.** C−B est l'énoncé C du skill : l'effet des cartes à base de
cas égale. C−A est la valeur ajoutée du dispositif entier — lecture, moteur et classe de référence —
sur un modèle seul. Les deux sont publiés, et ils ne répondent pas à la même question.

---

## 3 · Le déroulé d'une question

1. **Question.** Le bot récupère les questions ouvertes du tournoi (MiniBench par défaut).
2. **Bras A.** Le modèle seul répond ; la réponse est scellée.
3. **Plan.** Le modèle dit quel événement correspond au OUI, ce qu'il faut chercher pour le taux de
   base, et ce qu'il faut chercher pour la lecture. Le bot vérifie la forme du plan et le renvoie une
   fois s'il est mal formé. La **strate est choisie à l'aveugle** : le plan ne sait pas quelles strates
   le moteur chiffre (L7), pour que l'étiquette ne soit pas tirée vers celle qui ouvre le calcul.
4. **Bras B.** Recherches de taux de base, puis recherche de questions **déjà résolues** d'apparence
   voisine sur Metaculus — leur **issue seulement**, jamais les prévisions publiées de la communauté.
   La classe de référence est **définie une fois** (ce qui compte pour un cas, sur quelle population,
   sur quelle période), puis **comptée trois fois indépendamment** sur cette même classe. B est la vue
   **médiane**, avec sa source ; l'écart entre les trois comptages est enregistré comme dispersion de
   mesure. Une source postérieure à la date du jour, ou qui se déclare « de mémoire », est refusée ;
   au moins cinq questions résolues doivent compter le même type d'événement.
5. **Bras C.** Douze recherches de lecture au plus, les autres notées « non cherchées » ; le modèle
   écrit un dossier à partir des seuls résultats ; le moteur le juge et calcule. Un refus est renvoyé
   au modèle pour correction, deux fois au plus. **Le moteur reste juge : le bot ne fabrique aucun
   chiffre.** Si la lecture n'ancre aucune carte alors que des candidates ont été écartées faute de
   recherche (`aucun_fait`, `non_cherchee`), une relance ciblée de six recherches précède l'état nul ;
   celui-ci est ensuite qualifié `structure_absente` ou `angle_mort`, et la dynamique observée est
   décrite sans nommer de carte, hors calcul.
6. **Choix du bras posté.** Selon la règle du §4, avec un commentaire public qui l'explique.
7. **Registre.** Une ligne scellée par question : trois bras, bras posté, statut, `publie`, `mode`,
   commentaire envoyé, et le dossier de lecture horodaté dans `registre/dossiers/`.

Pour les questions **non binaires** — numériques, choix multiple, dates — le bot se comporte comme le
bot modèle (bras A) et journalise à part, dans `registre/journal-autres.jsonl`.

---

## 4 · Ce que le bot poste, et pourquoi

| Situation | Bras posté |
|---|---|
| Le moteur du skill donne une probabilité | **C** |
| La lecture ne trouve aucune structure (« état nul »), relance comprise | **B**, le taux de base non ajusté |
| Pas de taux de base honnête, question hors du champ du skill, lecture refusée, erreur | **A** |

La règle est **conservatrice par construction** : le bot ne poste C que lorsque le moteur a chiffré, et
il ne présente jamais un état nul comme un accord avec le taux de base — un état nul est suivi à part,
par nature (`structure_absente` ou `angle_mort`), avec la tenue de B et son gain sur le modèle seul.

Aujourd'hui, le skill ne chiffre que la strate 7 (décision L7). Hors de ce domaine, le bot **enregistre
B** et **poste A**. Cette règle ne changera pas avant la levée de L7, et la levée a un critère écrit
d'avance (§7).

---

## 5 · Les quatre apports à l'Alphabet

### 5.1 · Des épisodes prospectifs, scellés, à la cadence qu'exigera V4

Le jalon V4 demande des épisodes **préenregistrés** : prévision publiée chez un tiers horodaté avant
l'échéance, dossier scellé avant le calcul, issue constatée ensuite. Un analyste humain en produit
quelques-uns par mois ; le bot en produit jusqu'à cinq par jour, chacun avec ses trois bras et son
dossier. C'est la seule pièce du dispositif qui puisse approcher les **50 épisodes** du plancher V4 —
et, si σ̂(d) vaut 0,15 à 0,20, les 300 à 500 que le §1.4 de la note juge nécessaires.

**Une limite d'admission, qu'il faut dire avant de compter.** Un épisode n'entre dans V4 que si les
cartes qu'il ancre figurent sur la **liste des cartes admises** — verdict `accord` au moins
« provisoire » — publiée avec son empreinte avant l'épisode 1 (`validation.md` §11.9) ; un état qui
ancre une carte hors liste rend l'épisode hors V4 (motif `codage`). Aucune carte n'a d'accord mesuré
aujourd'hui. Les épisodes du bot sont donc des **prévisions préenregistrées**, pas encore des épisodes
de V4 : ils le deviendront le jour où la liste existera. Le premier usage mesurable du bot n'est donc
pas V4, c'est le **critère de levée de L7** (§27), qui ne demande pas cette liste — et c'est une raison
de plus de ne pas confondre les deux seuils.

**Une distinction qu'il ne faut pas perdre.** Le bot ne remplit **pas** la base de cas. Une question
enregistrée n'est pas un cas codé : elle n'entre ni dans `assets/base-de-cas`, ni dans le calcul des
homologues, ni dans κ. Le bot établit le fondement empirique de la **revendication de prévision** —
l'alphabet bat-il un taux de base ? —, pas celui de la **base de cas** — les cartes sont-elles bien
codées ? Les deux fondements sont nécessaires ; le bot ne fournit que le premier. Confondre les deux
serait le contresens le plus coûteux que ce dispositif puisse inspirer.

### 5.2 · Des règles de mesure que le skill a reprises (0.7.50)

Le bot a changé sa façon d'enregistrer et de mesurer entre ses versions 0.1 et 0.5.1, après un audit
externe, deux relectures et une veille. La 0.7.50 les a reportées dans `validation.md` §28, **sans
toucher un paramètre, une règle de décision ou une probabilité** ; le gel du §14 reste la règle. Six
points méritent d'être retenus, parce qu'ils sont devenus des règles du skill :

1. **La vue extérieure en deux temps.** Constat du registre : sur une même question, trois estimations
   du taux de base allaient de 0,2 % à 8 %, parce qu'elles ne comptaient pas la même classe (« 0 cas
   sur 22 périodes biennales », « 0 sur 46 présidences », « 1 sur 11 fenêtres glissantes »). Une
   médiane de trois **classes** n'est pas une médiane : c'est un tirage (Hájek, *Synthese* 156, 2007).
   La règle est désormais : définir la classe, puis compter ; retenir la vue médiane avec sa source,
   jamais une moyenne qui fabriquerait un chiffre ; consigner la dispersion comme variance de mesure.
2. **La strate à l'aveugle.** La même question a été lue SEUIL@13, puis SEUIL@7 après que la consigne
   eut mentionné que seule la strate 7 se chiffre. La strate se choisit donc **avant** de consulter
   `strates_prevision`, et la stabilité de l'étiquette ne se mesure qu'à version égale.
3. **L'état nul qualifié.** Chaque rejet porte sa catégorie — `aucun_fait`, `non_cherchee`,
   `marqueur_non_rempli`, `contredit` — et dit ce qu'aurait montré un fait suffisant. Seul `contredit`
   renseigne sur l'alphabet lui-même ; les trois autres mesurent l'écart entre ce que le codeur sait et
   ce qu'il ancre.
4. **Deux scores, deux usages.** Le tournoi note au **score logarithmique** ; le critère de levée de L7
   reste en **Brier**, parce que le skill ne dépend pas du règlement d'un tournoi. Le bot rapporte les
   deux, et le lecteur ne les confond pas : une question compte une fois, sa dernière prévision
   publiée, bornée à [0,001 ; 0,999].
5. **L'inférence valide à tout instant.** Le score se lit par une **séquence de confiance** et un test
   séquentiel par pari (Waudby-Smith & Ramdas, *JRSS-B* 2024 ; Choe & Ramdas, *Operations Research*
   2024) : on peut consulter le score chaque semaine sans fausser la conclusion. Le verdict a trois
   valeurs — « meilleur », « moins bon », « **indéterminé** » — et seule l'hypothèse fixée d'avance (C
   fait mieux que B) est testée au niveau α ; les trois autres comparaisons, faites sur les mêmes
   questions, au niveau α/3. La 0.7.51 a reporté cette inférence dans `scorer`, pour que le skill et le
   bot ne puissent pas conclure différemment sur la même décision.
6. **Le sens unique de C, mesuré, pas corrigé en silence.** Tous les λ étant ≥ 1, pour un événement
   « apparait » C ne peut que monter au-dessus de B : il gagne sur les OUI, perd sur toutes les NON, et
   surestime en moyenne si B mêle des situations avec et sans cartes. Le bot mesure ce biais
   (`biais_C`) et apprend, sur des **tests rétrospectifs**, un seul paramètre : un décalage b en logit,
   `p′ = logit p_C + b`, écrit seulement à partir de 15 questions chiffrées et s'il gagne hors
   échantillon. La prévision corrigée est scellée et scorée **en ombre**, jamais postée : la règle de
   postage ne change pas avant la levée de L7.

### 5.3 · Le goulot rendu visible : L7

Sur les trois premières questions réelles du bot, **deux relèvent de la strate 6** et la troisième ne
s'ancre sur aucune carte. Le moteur a donc refusé de chiffrer, et le bot a posté A ou B. Ce n'est pas
un incident : c'est la conséquence mécanique d'une décision d'auteur — le chiffre est limité à la seule
strate 7, la seule dont 13 équivalents sur 16 sont sourcés, et une strate ne s'ajoute que lorsque ses
cartes ont un accord mesuré.

Le bot a rendu ce goulot **mesurable**, et c'est son apport le plus utile à la conduite du projet. La
0.7.49 a écrit le critère de levée **avant** de voir le moindre résultat, pour que le moment de la
levée ne soit pas choisi d'après eux : une strate s'ajoute à `strates_prevision` si, en strate 7, sur
au moins **20 questions géopolitiques résolues et prospectives** où B et C existent, la différence
appariée de Brier **C − B est ≤ 0**, et si la condition d'origine de L7 — accord mesuré, équivalents
Documentés — est remplie dans la strate visée. Une lecture scellée hors strate 7 reste admise ; elle
peut être chiffrée après coup, et ne compte jamais dans la première condition.

### 5.4 · Un instrument de mesure du protocole, pas un concurrent

Le bot n'est pas un rival de l'Alphabet : il est le banc d'essai de l'Alphabet. Il ne propose pas
d'ontologie, il n'ajoute pas de cartes ; il applique le skill et le score. C'est pourquoi il figure
dans ce dépôt comme document d'analyse et non dans `concurrents-directs.md` — sauf sur un point : il
occupe la place que le protocole 5 du banc d'essai réservait à un « bras externe », et il la rend
répétable.

---

## 6 · Ce que le registre contient au 5 novembre 2026

Trois questions binaires, **onze passages scellés**, du 4 novembre 2026 entre 00 h 59 et 04 h 33
(heure locale, +01:00). Le registre ne contient aucune question résolue, donc aucun score.

| Question | Objet | Fenêtre | Résolution prévue | Passages | B successifs | Statut de C | Posté |
|---|---|---|---|---|---|---|---|
| 43329 | Fortune du président américain ≥ 4× son niveau d'entrée (2025–2026) | 59 j | 2027-01-01 | 4 | 0,003 · 0,002 · 0,013 | refusé ×2, hors strate ×2 | A ×4 |
| 43330 | Même question, exercice 2027–2028 | 790 j | 2029-01-01 | 4 | 0,025 · 0,08 · 0,02 | refusé ×2, hors strate ×2 | A ×4 |
| 43332 | Un État de l'UE quitte l'Union avant 2027 | 89 j | 2027-01-31 | 3 | 0,003 · 0,003 | refusé, état nul ×2 | A, puis B ×2 |

À quoi s'ajoutent **treize lignes non binaires** sur sept questions distinctes (budget fédéral,
nomination présidentielle, loi martiale en Ukraine, approbation de Donald Trump, taux moyen de la
dette, sorties de responsables de l'exécutif, prévisionnistes d'une question), toutes au bras A.

Les lignes portent les versions du bot **0.1.1 à 0.1.6** et du skill **0.7.48 à 0.7.49** : elles
précèdent donc la version 0.5.1 décrite par le README et les règles du §28. Deux conséquences de
lecture, qu'il vaut mieux dire que découvrir :

- **Le champ `mode` n'existe pas dans ces lignes.** Le README de la 0.5.1 documente `mode` et `publie` ;
  les lignes de 0.1.x ne les portent pas. Le §27 du skill situe le premier passage en **zone de test**
  (2026-11-04) ; le registre, lui, ne permet pas de le vérifier ligne à ligne. C'est une réserve de
  traçabilité, non une contradiction.
- **L'adresse enregistrée ne désigne pas toujours la question.** Les quatre lignes de 43329 et de 43330
  portent `https://www.metaculus.com/questions/43325`, et les trois lignes de 43332 portent
  `…/43327` : ce sont d'autres questions du tournoi. Les **titres**, eux, correspondent aux identifiants.
  C'est un défaut du champ `url` des versions 0.1.x, à vérifier sur les lignes 0.5.1 avant de s'y fier
  pour retrouver une question.

Le registre est donc **mince, daté, cohérent dans ses statuts** — les dossiers existent exactement pour
les passages où une lecture a été lancée, et manquent pour les passages « hors strate », où elle ne
l'a pas été — et **non encore scoré**.

---

## 7 · Ce que ces chiffres disent

1. **La chaîne tourne de bout en bout.** Le bot a récupéré des questions réelles, calculé A, cherché un
   taux de base, écrit un dossier, fait juger par le moteur, scellé une ligne. Aucun chiffre n'a été
   fabriqué : quand le moteur a refusé, le bot n'a pas posté de C.
2. **La règle de postage a été appliquée sans exception.** Deux questions hors strate → A ; un état nul
   → B après la relance ; aucune question n'a produit de C. Le dispositif est donc, pour l'instant, un
   **générateur de taux de base et de témoins**, pas encore un test de l'alphabet.
3. **L7 est la contrainte liante, et elle est mesurée.** Deux questions sur trois en strate 6 : le
   moteur ne chiffre pas, et la comparaison C−B ne peut pas commencer. Ce n'est pas un défaut du bot ;
   c'est le prix de la décision d'auteur, et c'est exactement ce que le critère du §27 doit arbitrer.
4. **Le taux de base est instable d'un passage à l'autre.** Sur 43329, B passe de 0,002 à 0,013 (×6,5) ;
   sur 43330, de 0,02 à 0,08 (×4). Ce sont des passages différents, avec des recherches différentes —
   et c'est précisément le fait qui a justifié la règle « définir la classe, puis compter trois fois ».
   L'instabilité n'est pas corrigée par la médiane ; elle est rendue visible par la dispersion.
5. **Aucune conclusion de performance n'est possible.** Zéro question résolue, zéro C, zéro score. Le
   premier point de mesure tombe au plus tôt le **1er janvier 2027** (43329), et le dernier en 2029.

**Ce que le registre ne dit pas, et qu'on serait tenté de lui faire dire.** Il ne dit pas que les cartes
ne servent à rien : il dit qu'elles n'ont pas été jouées sur ces trois questions. Il ne dit pas que le
taux de base est mauvais : il dit qu'il varie. Il ne dit pas que le bot échoue : il dit qu'il attend des
questions dans la seule strate que le skill chiffre, et des résolutions.

---

## 8 · Ce qu'il faudra pour conclure

| Question | Seuil | Où il est écrit |
|---|---|---|
| Les cartes abîment-elles le taux de base en strate 7 ? | **20** questions résolues, B et C présents, C − B ≤ 0 | `validation.md` §27 |
| L'alphabet bat-il la vue extérieure ? | statut V4 contre `vue_exterieure`, séquence de confiance à 1 − α | `validation.md` §19, §28 ; `scorer` 0.7.51 |
| Un gain de 10 points est-il détectable ? | environ **180** questions appariées à σ = 40 points ; 80 pour 20 points, 660 pour 5 | `validation.md` §28 |
| Le jalon V4 est-il franchi ? | **max(50, n(σ̂))** épisodes, gain absolu ≥ 2,5 points, test significatif | §1.4 de la note |
| Un épisode du bot est-il admissible dans V4 ? | cartes ancrées sur la liste admise (`accord` ≥ « provisoire », publiée avant l'épisode 1) | `validation.md` §11.9 |

Ces seuils ne se contournent pas par la cadence : le bot peut produire les questions, pas raccourcir
les fenêtres. Avec des questions de 59 à 790 jours et cinq questions par jour au plus, dont une fraction
seulement relève de la strate 7, **vingt questions résolues demandent des mois, pas des semaines** — et
la première n'arrive pas avant janvier 2027. C'est la raison pour laquelle la note continue de dire
qu'aucune performance n'est acquise, tout en reconnaissant que le dispositif existe.

---

## 9 · Les limites

- **Pas d'humain dans la boucle** (règle du tournoi). Le bot mesure « le skill joué par un modèle », pas
  le skill codé par un humain. Il ne satisfait donc **pas** A4, qui exige au moins un codeur humain :
  un accord entre le bot et lui-même ne vaut pas un κ.
- **Les multiplicateurs sont hypothétiques** : aucun cas réel n'est actif dans le skill. C'est
  précisément ce que C−B éprouve, et c'est ce qui rend le test nécessaire plutôt que flatteur.
- **La recherche peut ramener des prévisions publiées.** Le plan l'interdit et le §26 du skill borne la
  fuite des tests rétrospectifs, mais une recherche web n'est pas un filtre ; le bras A, lui, n'a pas
  cette consigne. Sur des questions prospectives, le risque est plus faible ; il n'est pas nul.
- **La stabilité du taux de base** n'est pas acquise : elle a varié d'un facteur 6,5 sur une même
  question. Si la dispersion reste forte, la classe devra être contrainte davantage — et c'est un
  chantier de données, pas de rédaction.
- **Le skill ne chiffre qu'un domaine.** Tant que L7 tient, le bot accumule surtout des A et des
  B : un registre de témoins n'est pas un test de l'alphabet.
- **Le commentaire public est en anglais**, avec les indicateurs du moteur en français.
- **La correction du biais de C reste en ombre** et n'est écrite qu'à partir de 15 questions chiffrées :
  elle ne peut pas encore exister, faute de C.
- **Le plafonnement et la recalibration sont étudiés, non appliqués** : ce sont des décisions d'auteur
  réservées, et le plafonnement changerait le score du tournoi, pas la mesure de C−B.
- **Le registre lu ici est celui du 4 novembre**, produit par des versions 0.1.x. Il ne renseigne pas
  sur le comportement de la 0.5.1, dont les champs et les règles de mesure ont changé.

---

## 10 · Comment le vérifier

Le bot se contrôle sans réseau, et c'est ce qui rend ses affirmations vérifiables :

```
ALPHABET_SKILL_DIR=alphabet-situationnel python -m unittest discover -s tests
```

Modèle et recherche simulés, **vrai moteur du skill** ; ces tests tournent, avec l'audit du skill, à
chaque modification du dépôt (workflow « Contrôle du bot alphabet »). En local, le passage à blanc est
réservé à la zone de test :

```
cp .env.template .env      # remplir jeton, clé de modèle, clé de recherche
uv run python alphabet_bot.py --mode test_questions --sans-publier
```

Le score se calcule depuis le registre, avec une source d'issues :

```
python score_registre.py --metaculus            # interroge l'API, n'écrit rien sans --enregistrer
python score_registre.py --resolutions issues.jsonl
```

À la date de ce document, aucune issue n'est fournie dans le dépôt : le scorer n'a rien à apparier.
Le relevé du §6 se refait à la main, en lisant `registre/journal-bot.jsonl` (une ligne JSON par
passage) et `registre/dossiers/` (un dossier par lecture effectivement lancée).

---

## 11 · Sources

- `Othman-Benbrahim/metac-bot-template`, `README-alphabet.md`, version 0.5.1 (bot), skill 0.7.51 ;
  `ABSTRACT-alphabet.md` ; `alphabet_pipeline.py` (`VERSION_BOT = "0.5.1"`) ; `score_registre.py` ;
  `tests/` ; workflows `run_alphabet_bot.yaml`, `score_alphabet.yaml`, `retro_alphabet.yaml`,
  `ci_alphabet.yaml`.
- `Othman-Benbrahim/alphabet-situationnel`, `references/validation.md` §27 (critère de levée de L7,
  0.7.49) et §28 (alignement avec le bot, 0.7.50, et levée du gel pour `scorer`, 0.7.51) ;
  `SKILL.md` ; `references/feuille-de-route.md`.
- Registre lu : `registre/journal-bot.jsonl` (11 lignes), `registre/journal-autres.jsonl` (13 lignes),
  `registre/dossiers/` (6 dossiers), au 5 novembre 2026.
- Hájek, A. « The reference class problem is your problem too », *Synthese* 156, 2007.
- Waudby-Smith, I., Ramdas, A. « Estimating means of bounded random variables by betting »,
  *JRSS-B* 86(1), 2024 ; Choe, Y., Ramdas, A. « Combining Evidence Across Filtrations Using
  Adjustably Truncated Online e-Statistics », *Operations Research*, 2024.
- El Lahib, M. et al. arXiv:2602.00758, 2026 ; Paleka, D. et al., ICLR 2026, arXiv:2506.00723 —
  fuites temporelles des évaluations rétrospectives (citées au §26 du skill, et qui bornent ce que le
  bot peut apprendre de ses propres tests rétrospectifs).

*Document rédigé le 5 novembre 2026 sur le registre du 4 novembre. Les comptes de lignes et de champs
sont reproductibles par lecture des fichiers cités ; aucun score n'est cité, parce qu'aucun n'existe.*
