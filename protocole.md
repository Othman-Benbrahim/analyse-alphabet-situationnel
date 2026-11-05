# Protocole adopté, et ce qu'il reste à faire

> **Version du document : 0.7.51 · révision 1 · 5 novembre 2026.**
> Protocole aligné sur la version **0.7.51** du dépôt
> [`Othman-Benbrahim/alphabet-situationnel`](https://github.com/Othman-Benbrahim/alphabet-situationnel)
> (licence MIT), étiquette `v0.7.51`, vérifiée le 5 novembre 2026.
>
> Les cinq documents d'analyse de ce dépôt portent la même version. Le dispositif qui produit les
> premiers épisodes prospectifs — le bot Metaculus — est décrit dans [`bot-metaculus.md`](bot-metaculus.md) ;
> il ne change aucune règle de ce document, mais il change l'ordre pratique des chantiers, et le §2 le
> dit.

---

## 0 · Ce que ce document est, et à qui il s'adresse

Cinq documents cohabitent ici et ne jouent pas le même rôle.

| Document | Rôle | Autorité |
|---|---|---|
| [`analyse-alphabet-situationnel.md`](analyse-alphabet-situationnel.md) | **juge** : ce que le dépôt vaut, ce qu'il prouve, ce qu'il ne prouve pas | une lecture critique, datée |
| [`concurrents-directs.md`](concurrents-directs.md) | **situe** : ce que les seize rivaux font mieux ou moins bien | une comparaison, datée |
| [`comprendre-l-alphabet-situationnel.md`](comprendre-l-alphabet-situationnel.md) | **explique** : la moitié sémiotique, la moitié mathématique, et leur couture | une vulgarisation, datée |
| [`bot-metaculus.md`](bot-metaculus.md) | **mesure** : le dispositif à trois bras, son registre, ce qu'il a produit | un relevé daté |
| ce document | **prescrit** : ce que le protocole engage, ce qui reste, comment un collaborateur s'y insère | un mode d'emploi, révisable |

Ce document ne fait pas autorité sur les règles. En cas de désaccord, le dépôt fait foi, et dans l'ordre :
`SKILL.md`, puis `references/constitution.md` (P1–P9), puis `references/protocole.md` (O, A, G, B, T, S, V),
puis `references/validation.md` pour les règles de décision du test final. Chaque affirmation de ce
document renvoie à la section qui la porte, et chaque chiffre à la commande qui le produit.

**Quatre lecteurs, quatre entrées.**

- Un **second codeur** commence au §3.4, puis suit le §3.6.
- Un **tiers** commence au §4, et lit le §6 pour savoir ce qu'il devra signer.
- Un **méthodologue extérieur** commence au §5, qui contient la grille de relecture.
- L'**auteur** lit le §2 pour l'ordre des chantiers, et le §6 pour la liste de contrôle qui ouvre ou ferme
  l'épisode 1.

**Une règle de lecture, valable partout ensuite.** Un chiffre sans commande n'est pas un résultat ; une
règle sans section n'est pas une règle ; un seuil franchi après avoir vu les données n'est pas un seuil.
Les trois interdits sont la même idée, et c'est celle qui structure tout le dépôt analysé.

---

## 1 · Le protocole adopté

### 1.1 · Ce qu'il promet, et ce qu'il refuse de promettre

Le protocole prend un engagement étroit et un refus large.

**Il promet** : un état daté d'une situation, écrit dans une grammaire finie (seize cartes, treize
strates), appuyé sur des faits sourcés et datés, avec les contre-observations cherchées et classées, les
questions qui départagent les cartes voisines, et une probabilité accompagnée du **niveau de provenance**
ρ — c'est-à-dire de la nature de ce qui la soutient, jamais de sa fiabilité mesurée.

**Il refuse** : de présenter `p` comme une probabilité calibrée ; de répondre à une question causale (« que
produirait telle action ? ») ; de certifier la vérité d'un fait ; de valider un instrument par son
élégance. Le moteur est **associationnel** (barreau A de Pearl) : il extrapole des motifs observés. Toute
sortie se lit « si le motif observé se répète, alors… ».

Le refus n'est pas de la prudence rhétorique : c'est une conséquence. Les 66 transitions du graphe sont
postulées, et le principe P1 interdit d'en poser une qui ne soit pas transposable entre strates ; sans
identification causale, une intervention ne se calcule pas. Le dépôt écrit cette limite dans `SKILL.md`,
pas dans une note de bas de page.

Ce qui reste possible, et qui est déjà beaucoup : **mesurer si l'instrument fait mieux que ses propres
comparateurs**. C'est l'objet du test final, et c'est la seule chose qui puisse transformer un cadre
cohérent en instrument éprouvé.

### 1.2 · La chaîne, en sept gestes

| Geste | Règle | Ce que le moteur contrôle | Ce qu'il laisse au jugement |
|---|---|---|---|
| Rattacher la situation à des strates | O1 | — | le choix des strates par les faits, non par le sujet |
| Ancrer un fait dans une carte | A1, A6 | forme de la ligne A6, verdicts, justification non vide | la vérité du fait, la justesse de la justification |
| Écrire l'état | G2, G6 | syntaxe, voisines, incompatibilités, qualificatifs | la pertinence des liaisons |
| Écrire la fiche du cas | B1, B5 | schéma complet, partage daté par empreinte, registre | la lecture de la source |
| Estimer la transition | T3 | éligibilité, disponibilité à la date figée, poids | l'identité causale des homologues |
| Publier avec son niveau | S4 | cohérence du ρ avec le nombre de cas | le choix du comparateur |
| Journaliser et scorer | V1, V4 | empreintes, résolution externe, absence de doublon | l'exactitude de la résolution |

La chaîne est **séquentielle et bloquante** : un état mal formé n'entre pas dans la base ; un cas non
partagé avant codage rend la fiche non valide ; une fiche active invalide bloque le calcul de toute la
base. Ce n'est pas de la sévérité décorative : c'est ce qui permet de dire, plus tard, que le nombre
publié correspond à une lecture faite avant l'issue.

### 1.3 · Les huit règles qui portent l'engagement

| Règle | Ce qu'elle exige | Ce qu'elle interdit | Instrument |
|---|---|---|---|
| **A1 · ancrage** | un fait de la strate remplit un marqueur de l'équivalent local, sinon l'ancrage passe par le noyau et plafonne à f | un ancrage par le nom de la carte | `valider` |
| **A3 · statut des équivalents** | Documenté = référence vérifiée soutenant la traduction **et** ses marqueurs | promouvoir sur un résumé, sur une bibliographie, ou pour « fabriquer une attestation » | `audit`, `equivalences` |
| **A4 · accord entre codeurs** | ≥ 20 cas par strate **et** 20 % des cas de la strate, codés indépendamment par deux codeurs, dont au moins un humain | publier un κ sans son intervalle, ou un accord humain–modèle comme s'il valait un accord humain–humain | `accord` |
| **A6 · force et voisines** | F exige un fait précis, un marqueur local, **et** chaque voisine tranchée avec justification | un `?` sur une voisine pour un mot F ; une force qui exprimerait une intensité | `valider` |
| **A7 · anti-résonance** | chercher la contre-observation la plus forte **dans la situation**, puis classer sa portée | un contre-exemple pris ailleurs ; conclure sans dire où l'on a cherché | `dossier`, `valider` |
| **B3 · double codage** | ≥ 20 % des cas de chaque strate codés par deux codeurs indépendants | deux passes du même modèle comme deux codeurs | `bilan` |
| **B5 · partage** | l'usage (apprentissage ou test) est figé **avant** le codage, daté, par empreinte de l'identifiant | changer un cas de lot après avoir vu son issue | `partager`, `valider --registre` |
| **V4 · jalon de validation** | un différentiel de Brier absolu, testé, contre des comparateurs, sur des épisodes préenregistrés | appeler « validation » un gain relatif non testé, ou une lecture répétée d'un test exact | `scorer` |

Deux règles méritent d'être lues deux fois, parce que tout le reste en dépend.

**A4 n'est pas une formalité statistique.** C'est la réponse à l'objection la plus ancienne adressée à ce
genre d'entreprise : Durkheim, en 1900, objectait à Simmel que séparer la forme du contenu n'est pas
prouvé, que le niveau de généralité où l'on coupe est arbitraire, que les exemples sont « choisis plus ou
moins au hasard », et que la preuve se réduit à une suite d'exemples. Les quatre objections valent pour
l'Alphabet. La réponse du dépôt n'est pas un argument, c'est une mesure : accord entre codeurs,
anti-résonance, cas sans événement, scores sur des questions résolues. **Tant que la mesure n'a pas
commencé, l'objection reste ouverte** — c'est écrit dans la règle A2 elle-même.

**V4 ne mesure pas la vérité du modèle.** Il mesure un écart de Brier entre l'alphabet et un comparateur
fixé, sur des épisodes préenregistrés. Le seuil de 2,5 points vaut 10 % d'un Brier de 0,25 ; il est choisi
pour détecter de **grands** effets, et le dépôt publie d'avance le tableau de puissance qui montre qu'un
apport vrai de 2 à 4,5 points finira le plus souvent « non établi ». Ce n'est pas un défaut du test : c'est
son domaine de validité, écrit avant la mesure.

### 1.4 · L'état mesuré au 5 novembre 2026

Relevé sur un clone propre de l'étiquette `v0.7.51`, sans fichier local ajouté.

```
python scripts/moteur.py audit
  → conforme — 49 fichiers au manifeste, 208 statuts, 393 renvois §,
    paramètres exhaustifs, matrice et inerties, schéma de fiche validé

python scripts/moteur.py autotest
  → 167 tests (160 passent sous un bac à sable qui refuse le dossier temporaire ; 7 refus d'écriture)

python scripts/moteur.py bilan
  → Étape 2 · 0 cas actif · 0 proposition · 4 archives
    Étape 3 · 13/16 équivalents Documentés ou Attestés (strate 7) · 0 strate complète · 1/14 cases Vides closes
    Étape 4 · aucune référence externe
    Étape 5 · aucun cas actif
    Test à l'aveugle · aucun journal
```

| Jalon | État | Ce que cela signifie |
|---|---|---|
| Cadre et moteur | **complet** | 167 autotests, audit conforme, paramètres exhaustifs |
| Cas réels actifs | **0** | la base est vide ; les quatre premiers cas sont archivés, exclus de tout calcul |
| Équivalents sourcés | **13 / 208** | tous en strate 7 ; l'emprunt entre strates (T4) reste fermé |
| Accord entre codeurs | **non mesuré** | aucune carte n'a de table 2×2 : c'est le verrou du §3 |
| Épisodes prospectifs (bot) | **3 questions · 11 passages · 0 résolue** | aucun `C` ; non admissibles dans V4 sans la liste des cartes admises |
| Test final (V4) | **non commencé** | 0 / 171 épisodes, et il ne peut pas commencer |
| Performance prédictive | **aucune** | rien n'a été démontré, et le dépôt ne le prétend pas |

Ce tableau se lit dans un sens unique : **tout ce qui est en haut est fait, tout ce qui est en bas
demande des données humaines.** Le dépôt a fermé des dizaines de défauts de méthode et zéro défaut
empirique. Un instrument qui en est là a fait son travail de méthode ; il n'a pas commencé son travail de
mesure.

### 1.5 · Le protocole de ce dépôt-ci

Il est plus léger, et il doit rester vérifiable.

1. **Une version, une révision, une date** en tête de chaque document. La version suit celle du dépôt
   analysé ; la révision compte les réécritures à version constante.
2. **Une correction ne réécrit pas l'histoire.** `CHANGELOG.md` conserve l'entrée fautive et nomme ce qui
   a changé.
3. **`SHA256SUMS` couvre les fichiers livrés** et se régénère à chaque livraison ; il ne se couvre pas
   lui-même. Une livraison par l'interface web peut réécrire les fins de ligne et invalider les
   empreintes : vérifier le manifeste **après** chaque envoi, pas seulement avant. Le cas s'est produit
   sur ce dépôt — les empreintes publiées ne correspondaient plus aux fichiers livrés, sans qu'aucune
   conclusion ait changé.
4. **Une version livrée se retrouve par son étiquette** `vX.Y.Z`, jamais par la lecture d'un fichier.
5. **La troisième personne.** Ces documents parlent du dépôt et de son auteur à la troisième personne,
   pour rester lisibles hors du dialogue qui les a produits.
6. **Un document qui change d'alignement le déclare** en tête. Depuis la 0.7.51, les cinq documents
   d'analyse sont alignés sur la même version du dépôt, et le disent ; il n'y a plus de document en
   avance sur les autres.

---

## 2 · Ce qu'il reste à faire

### 2.1 · L'ordre, et pourquoi il n'est pas négociable

```
   cas réels codés (étape 2)
            │
            ├──► double codage de 20 cas  ──►  ÉTUDE D'ACCORD  ──►  liste des cartes admises, scellée
            │                                                              │
            │                                                              ├──► accord prospectif
            │                                                              │    (20 % des états de V4,
            │                                                              │     recodés par le tiers)
            │                                                              ▼
            └──────────────────────────────────────►  fiche d'étude + relecture externe  ──►  ÉPISODE 1
                                                                                    │
                                                                                    ▼
                                                                     V4 · 171 épisodes, 2 énoncés
                                                                      ▲
   bot Metaculus (en parallèle) : questions → 3 bras scellés → issues ─┘
     · critère de levée de L7 (§27) : évaluable dès 20 questions résolues
     · V4 : seulement une fois la liste des cartes admises publiée
```

La chaîne n'est pas un ordre de préférence, c'est une dépendance logique, et le dépôt l'écrit sans
détour : « Aujourd'hui aucune carte n'a d'accord mesuré : **V4 ne peut pas commencer** avant cette
étude. » La raison est simple. Un épisode de V4 n'est admis que si les cartes qu'il ancre sont sur une
liste dont l'accord a été vérifié ; sans liste, il n'y a pas d'épisode admissible ; sans épisode, pas de
score ; sans score, pas d'énoncé.

**Le bot ne change pas cette dépendance, et il faut le dire nettement.** Il produit dès maintenant des
épisodes préenregistrés, et le **critère de levée de L7** (§27) peut être évalué sans la liste : vingt
questions géopolitiques résolues, B et C présents, C − B ≤ 0. Mais un épisode n'entre dans V4 que si ses
cartes sont sur la liste admise. Le bot remplit donc le pipeline ; il ne le débloque pas. La distinction
compte, parce qu'elle sépare deux échéances : L7 peut être tranché avant l'étude d'accord, V4 non.

### 2.2 · Le tableau des restes

| Priorité | Chantier | Ce qu'il débloque | Bloqué par |
|---|---|---|---|
| **P0** | Coder 20 cas réels de strate 7 sous les règles courantes | la base, l'étude, tout le reste | rien — c'est le point de départ |
| **P0** | **Étude d'accord** sur ces cas, deux codeurs humains (§3) | la sortie du mode solo, ρ0, la crédibilité de la base | les 20 cas |
| **P0** | **Tiers nommé**, publié avant l'épisode 1 (§4) | le droit de publier un résultat non « exécuté par l'auteur » | le choix d'une personne |
| **P0** | **Relecture par un méthodologue extérieur** (§5) | la validité de la fiche d'étude et du §11 | la fiche écrite |
| **P0** | Fiche d'étude horodatée chez un tiers (§3.12, §6) | l'épisode 1 | les quatre lignes ci-dessus |
| **P0** | Évaluer le critère de levée de L7 sur les 20 premières questions résolues (§27 du skill) | le chiffre dans une seconde strate | les questions et le temps — le bot les produit |
| **P1** | V4 : 171 épisodes, deux énoncés séparés (C et A) | la seule conclusion confirmatoire possible | la porte du §6, **et la liste des cartes admises** |
| **P1** | Laisser tourner le bot et scorer le registre | les épisodes préenregistrés de V4 | le temps ; 3 questions et 0 résolue au 5 novembre 2026 |
| **P1** | Test de leurres : 40 situations, 26 reconnues sur 40 | le mode LIRE publié, ou publié « non distingué d'un leurre » | des juges étrangers au projet |
| **P2** | Compléter la strate 7 (1 Proposé, 2 Vides) | l'emprunt T4, l'étape 0.8 | du temps de lecture, pas des données |
| **P2** | Bibliothèque de fréquences externes (étape 4) | le passage de ρ4 à ρ3 | des sources publiées |
| **P2** | 0.8 / 0.9 / 1.0 du dépôt analysé | la structure, puis la grammaire | 30 cas actifs, un rédacteur indépendant |

### 2.3 · Deux chantiers distincts, souvent confondus

Ce dépôt-ci a ses propres restes, qui ne sont pas ceux du protocole.

| Reste du protocole | Reste de cette note |
|---|---|
| l'étude d'accord, le tiers, la relecture externe | étiqueter `v0.7.51` et publier `SHA256SUMS` |
| les 20 cas réels de strate 7 | vérifier le manifeste **après** l'envoi |
| V4 et les leurres | trancher la licence du texte (CC BY 4.0 proposé) |
| la complétion de la strate pilote | — |

Le second point mérite une phrase. La présente révision est celle qui remet la note d'aplomb : elle
passe de 149 à 167 autotests, de 47 à 49 fichiers au manifeste, de 248 à 393 renvois §, et elle ajoute
le document sur le bot. Elle ne prétend pas mesurer autre chose : la clôture donne la même empreinte
qu'en 0.7.15 sur les 2 790 conséquences, donc aucune probabilité n'a bougé. Ce qui a bougé, c'est ce
que le dépôt **sait de lui-même** — ses tests, ses limites, son registre.

---

## 3 · L'étude d'accord — le chantier prioritaire

### 3.1 · La phrase du programme, décomposée

> « une étude d'accord sur des cas réels codés par deux personnes, un tiers nommé, et une relecture par un
> méthodologue extérieur. »

La phrase contient quatre exigences et une sortie implicite ; le tableau les décompose en six lignes.
Chacune a une section qui la porte, et un instrument qui la vérifie ou qui constate son absence.

| Élément | Ce que le protocole en fait | Où c'est écrit | Instrument |
|---|---|---|---|
| **étude d'accord** | une mesure de reproductibilité inter-codeurs par carte, avec table 2×2, intervalles et verdict | A4 ; `validation.md` §11.8 | `accord` |
| **sur des cas réels** | des fiches actives, sourcées, dont l'issue est connue ; jamais la démonstration fictive | B1, B3 ; `moteur.py bilan` | `valider` |
| **codés par deux personnes** | deux codeurs distincts, dont au moins un humain ; la consigne de l'auteur est plus stricte que la règle et retient **deux humains** | A4, B3 ; `validation.md` §11.1 | `bilan` (`mode solo`) |
| **un tiers nommé** | une personne désignée **avant** l'épisode 1, qui exécute le score, juge les leurres, recode 20 % des états, et publie son rapport | `validation.md` §11.7, §11.9-7, §11.12 | déclaratif |
| **une relecture par un méthodologue extérieur** | un biostatisticien ou un méthodologue qui n'a pas participé à l'écriture, relit la fiche et le §11 ; rapport publié avec la fiche | `validation.md` §11.13-6 | déclaratif |
| ***(implicite)* la liste des cartes admises** | la sortie de l'étude : les cartes dont le verdict est au moins `provisoire`, publiées avec leur empreinte, gelées avant l'épisode 1 | `validation.md` §11.8 | `accord` + empreinte |

**Une remarque sur « deux personnes ».** La règle A4 autorise un modèle de langage comme l'un des deux
codeurs (`role: modele`), et exige seulement qu'un humain soit de la partie. La consigne de l'auteur va
plus loin, et elle a raison : A4 elle-même explique pourquoi. Un modèle est **anthropomimétique** —
entraîné à produire les produits observables de la lecture humaine, il les produit que la lecture ait eu
lieu ou non. Un accord élevé entre un humain et un modèle mesure au mieux la convergence de deux
producteurs de lectures plausibles, au pire l'imitation par le modèle de ce qu'un humain aurait écrit. Il
ne prouve pas la fiabilité de la lecture. **Deux humains, donc.** Un accord humain–modèle peut se
publier, à part, comme une mesure de stabilité — jamais comme un κ.

### 3.2 · Pourquoi elle bloque tout

Trois verrous, et ils ne se forcent pas séparément.

**Le verrou logique.** L'objection de Durkheim reste ouverte tant qu'aucune mesure n'est faite. Les seize
cartes de départ n'ont pas suivi la procédure A2 (trois lacunes indépendantes, structure nommée, deux
strates) : elles sont donc « candidates », et le resteront aussi longtemps qu'un accord n'aura pas été
mesuré sur elles. Ce n'est pas une taie dans un dossier par ailleurs propre ; c'est le point où la
théorie attend un chiffre.

**Le verrou opérationnel.** `validation.md` §11.8 : l'accord se mesure **avant** le premier épisode, sur
des cas de la base, et la liste des cartes admises se publie avec son empreinte avant l'épisode 1 et ne
change plus. « Aujourd'hui aucune carte n'a d'accord mesuré : V4 ne peut pas commencer avant cette
étude. » V4 est le seul dispositif qui puisse produire une conclusion confirmatoire ; il est donc
entièrement suspendu à cette mesure.

**Le verrou de la base.** Sous 20 cas double-codés et 20 % de la strate, l'outil est en **mode solo**
(A4, B3) : ρ0 est inaccessible (`seuil_rho0_cas_distincts` = 30, mais un ρ0 sans double codage n'est pas
publiable), et une prévision ne peut pas prétendre s'appuyer sur une base. Le moteur le dit tout seul :
`bilan` affiche « aucun cas actif » et compte les double-codés à zéro.

Autrement dit : sans κ, pas de liste ; sans liste, pas d'épisode ; sans épisode, pas de score ; sans
score, pas de conclusion. Et une conclusion négative — « l'alphabet n'apporte pas plus de 2,5 points » —
serait déjà un résultat publiable, à condition d'avoir été mesurée. C'est la situation actuelle qu'il
faut changer, pas la théorie.

### 3.3 · Quatre fonctions, et le droit de les cumuler

Le protocole demande **quatre fonctions**, pas quatre personnes. Les confondre est l'erreur la plus
coûteuse possible ici, parce qu'elle ne se voit qu'à la publication.

| Fonction | Ce qu'elle fait | Ce qu'elle ne fait pas | Ce qu'elle signe |
|---|---|---|---|
| **Codeur 1** | code les états depuis les sources, applique A1–A7, remplit la fiche | ne lance pas le calcul d'un épisode ; ne choisit pas les seuils | la fiche, `codage.debut`, `sources_verifiees` |
| **Codeur 2** | code **les mêmes états** sans voir le premier codage | ne discute pas avant la fin ; ne recode pas après avoir vu l'autre | `signe_suffisant` daté, puis son codage |
| **Tiers** | exécute le score et le test de leurres ; recode 20 % des états de V4 ; publie son rapport | ne participe pas à l'écriture des règles ; ne code pas les cas de l'étude qu'il devra ensuite juger — une double casquette se déclare | sa déclaration d'indépendance, son rapport |
| **Méthodologue** | relit la fiche d'étude et le §11 avant l'épisode 1 | n'écrit pas le protocole ; ne décide pas d'un seuil après avoir vu des résultats | son rapport daté |

**Les cumuls.** Chaque cumul retire une garantie, et se publie.

| Cumul | Effet | Recommandation |
|---|---|---|
| codeur 1 = auteur | biais d'engagement ; c'est le cas par défaut du dépôt | admis, **déclaré** ; sans tiers, un résultat se publie « exécuté par l'auteur » |
| codeur 2 = tiers | la même paire mesure l'accord initial puis l'accord prospectif, et le tiers cesse d'être un auditeur extérieur : il devient partie au dispositif qu'il doit contrôler | à éviter si un quatrième volontaire existe ; sinon, publier le cumul et en tirer la conséquence |
| tiers = méthodologue | la relecture externe porte sur un texte que le même lecteur a contribué à faire vivre | à éviter : la relecture n'a de valeur que par un regard neuf |
| codeur 2 = méthodologue | impossible en pratique : il relirait une étude qu'il a codée | exclu |
| deux codeurs = deux passes d'un modèle | interdit par B3 : deux passes du même modèle partagent ses biais | exclu |
| codeur 2 = modèle seul, sans humain | interdit par A4 : au moins un humain | exclu |

**Le nombre de personnes utiles.** Quatre fonctions ne demandent pas quatre personnes : trois suffisent
dans le cas favorable (auteur-codeur, second codeur humain, tiers qui est aussi méthodologue si l'on
accepte de perdre la relecture indépendante), et quatre dans le cas propre (auteur, second codeur, tiers,
méthodologue). La configuration à quatre est celle qui permet d'écrire, sans réserve, que le résultat n'a
pas été produit par la personne qui l'a conçu.

### 3.4 · Ce qu'on mesure : la décision, pas le cas

**L'unité est la décision codée : carte × strate × état.** Pas le cas, pas la fiche, pas le mot. Un cas de
trois états engage au plus 48 décisions — seize cartes fois trois états — mais seules comptent celles que
les deux codeurs ont réellement examinées.

C'est le point que la feuille de route a chiffré en 0.7.5 et que personne n'a encore appliqué : avec
`pₑ` = 0,5, distinguer κ = 0,80 de κ = 0,60 demande environ **83 décisions codées** ; distinguer 0,75 de
0,60 en demande 156. Vingt cas peuvent donc suffire ou non, selon leur densité : le compte se fait, il ne
s'estime pas.

**La table 2×2.** Pour une carte donnée, sur l'ensemble des états codés :

|  | Codeur 2 ancre | Codeur 2 n'ancre pas |
|---|---|---|
| **Codeur 1 ancre** | `a` — les deux | `b` — le premier seul |
| **Codeur 1 n'ancre pas** | `c` — le second seul | `d` — aucun |

**Les coefficients, et ce que chacun sert à faire.**

| Grandeur | Définition | Rôle ici |
|---|---|---|
| `pₒ` | (a + d) / n, l'accord observé | la base de tout |
| `pₑ` | p₁p₂ + (1−p₁)(1−p₂), l'accord attendu au hasard | dénominateur de κ |
| **κ** | (pₒ − pₑ) / (1 − pₑ) | publié, **jamais seul** : il s'effondre quand le code est rare, et devient indéfini à prévalence nulle |
| **PABAK** | 2·pₒ − 1 | **le verdict porte sur lui** : il ne s'effondre pas sous faible prévalence |
| **π de Scott** | marges regroupées | publié : κ et π peuvent tomber de part et d'autre du seuil sur les mêmes données |
| **α de Krippendorff** | nominal, deux codeurs | publié : le seul des trois qui s'étende à plus de deux codeurs, plus de deux valeurs et aux unités manquantes |
| **accord positif** | 2a / (2a + b + c) | la part d'accord **sur les présences** |
| **accord négatif** | 2d / (2d + b + c) | la part d'accord **sur les absences** |
| **manque du second** | b / (a + b) | un codeur n'est pas la référence de l'autre : les deux taux se publient |
| **manque du premier** | c / (a + c) | idem |
| **manque des absences** | b/(b+d) et c/(c+d) | sous forte prévalence, la valeur rare est l'**absence** : la même règle s'y applique |

**Les seuils, et ils ne se renégocient pas.**

| Paramètre | Valeur | Ce qu'il commande |
|---|---|---|
| `kappa_min` | **0,67** | verdict `provisoire` : seuil des conclusions provisoires |
| `kappa_rapportable` | **0,80** | verdict `rapportable` : seuil d'une fiabilité rapportable |
| `fnr_max` | **0,20** | aucun codeur ne manque plus de 20 % des ancrages de l'autre |
| `accord_min_ancrages` | **5** | sous ce nombre d'ancrages, la carte n'est pas estimable |
| `repetabilite_ecart_min_jours` | **30** | sous 30 jours, la seconde passe mesure la mémoire de la première |

**Les six verdicts que le moteur rend** — cinq pour l'accord entre codeurs, un réservé à la répétabilité.

| Verdict | Condition | Ce qu'on en fait |
|---|---|---|
| `sans objet` | aucun des deux codeurs n'ancre la carte | la carte est absente de l'échantillon : ce n'est pas un échec |
| `non estimable` | moins de 5 ancrages pour chaque codeur | le matériel ne permet pas de conclure ; ce n'est pas un échec |
| `insuffisant` | PABAK < 0,67, **ou** un codeur manque plus de 20 % des ancrages de l'autre | la carte retourne en Proposé ; on cherche la divergence de définition |
| `provisoire` | PABAK ≥ 0,67 et les deux taux de manque ≤ 0,20 | la carte entre sur la liste des cartes admises |
| `rapportable` | PABAK ≥ 0,80 et les deux taux de manque ≤ 0,20 | idem, avec une mention plus forte |
| `non recevable` | deux passes de répétabilité séparées de moins de 30 jours | la mesure ne se publie pas |

**L'intervalle, et le chiffre qui compte vraiment.** `accord` publie un intervalle approché de PABAK,
SE = 2·√(pₒ(1−pₒ)/n). À pₒ = 0,90 (PABAK 0,80), la borne basse vaut 0,54 à 20 décisions et ne dépasse
0,67 qu'à partir d'environ **82 décisions**. D'où la règle de lecture : **sous 82 décisions, un verdict se
lit « non évaluable », pas « échec »**. Et vérifier un seuil à 0,80 demanderait de l'ordre de **250
décisions** — vingt cas ne le feront pas. Vingt cas détectent un accord grossier ; ils ne certifient pas
une fiabilité rapportable.

Deux précautions que le moteur ne peut pas prendre à votre place. Les décisions d'un même cas ne sont pas
indépendantes : l'intervalle est **optimiste**, et 250 décisions ne valent pas 250 cas. Et PABAK est un
coefficient secondaire, emprunté aux repères de l'α de Krippendorff : il ne corrige pas du hasard réel et
devient indulgent sous forte prévalence. C'est pourquoi κ, π et α se publient avec lui, et pourquoi le
contrôle des absences existe.

### 3.5 · Le matériel : quels cas, combien, dans quelle strate

**Combien.** A4 demande **au moins 20 cas par strate** *et* **20 % des cas de cette strate**. Les deux
conditions, pas l'une ou l'autre. `bilan` compte les double-codés sur les mêmes critères
(`double_codage_min_cas` = 20, `double_codage_part` = 0,20) et sort du mode solo seulement quand les deux
sont atteints.

**Le problème d'ordre, qu'il faut nommer.** La base compte **zéro cas actif**. L'étude ne peut donc pas
être faite « sur la base » : elle **crée** la base. Coder vingt cas sous les règles courantes n'est pas
une formalité préalable, c'est la moitié du travail, et il doit être fait deux fois — une fois par codeur.

**Quelle strate.** La 7 (géopolitique), seule strate où un marqueur local a une référence lue. Elle
compte 13 équivalents Documentés, 1 Proposé (PÉRIODICITÉ) et 2 Vides (CROISSANCE, RÉSONANCE). Ce détail
n'est pas cosmétique : sur une carte Documentée, un désaccord s'interprète — les deux codeurs lisent le
même marqueur, et le désaccord porte sur le fait. Sur une carte Vide ou Proposée, le désaccord peut venir
du marqueur lui-même, et **l'étude ne peut pas dire lequel des deux a tort**. Deux conséquences :

- commencer par les treize cartes Documentées ; les trois autres se codent aussi, mais leur accord se
  publie avec la réserve que le marqueur n'est pas vérifié ;
- un désaccord persistant sur une carte Documentée est un **résultat sur la carte**, pas seulement sur les
  codeurs : il demande une révision du marqueur, et cette révision se publie.

**Quels cas.** Des cas **historiques**, dont l'issue est connue et les sources stabilisées. La raison a
deux étages. D'abord, l'accord se mesure avant l'épisode 1, sur des cas de la base, pas sur des épisodes
de V4 : il faut donc du matériel déjà résolu. Ensuite, un cas prospectif n'a pas d'issue au moment du
codage, et l'on ne peut pas mesurer l'accord sur des états dont la suite n'est pas établie.

Cela posera plus tard un problème que le dépôt a déjà identifié : **l'accord mesuré sur des cas dont
l'issue est connue est optimiste** — le codeur sait où l'histoire va. C'est pourquoi l'accord
**prospectif** existe séparément (§3.7), et c'est lui qui se lit pour V4.

**Cas sans événement.** Inclure des situations où la structure était présente et où rien ne s'est produit,
dans une proportion comparable à leur fréquence réelle. Sans eux, toute transition est surestimée — biais
du survivant. Attention : `sans_evenement: true` est plus strict qu'on ne le croit — il exige qu'aucune
apparition, disparition ni changement de force ne survienne sur **toute** la séquence. Une approche du
seuil qui change une force ne le permet pas.

**La fenêtre.** Trois mois par défaut (`fenetre_reference_jours` = 91,3125), identique dans tous les états
d'une même phrase, et deux états consécutifs séparés d'une fenêtre calendaire exacte. Un cas dont les
observations sont irrégulières s'archive ou se rééchantillonne explicitement — il ne se force pas dans un
pas régulier.

**Le compte des décisions.** Un état engage au plus seize décisions, une par carte. Un cas de deux états,
au plus trente-deux. Vingt cas, au plus 640. Ce sont des bornes hautes : une carte que les deux codeurs
n'examinent pas n'est pas une décision, et les cartes Vides de la strate se codent par le noyau. Le compte
réel s'établit au premier dépouillement, et c'est **lui** qu'on compare à 82 et à 250.

### 3.6 · La procédure, en onze étapes

Chaque étape a un responsable, une preuve et un interdit. Une étape franchie sans sa preuve ne compte pas.

**1 · Constituer le lot.** *Auteur.* Écrire la règle de sélection — strate, période, type d'issue, sources
disponibles — **avant** de regarder les cas candidats, puis la publier. Attribuer les identifiants
`C-NNNN-SNN`. La règle de sélection écrite après coup est une règle choisie sur les données.
> *Interdit :* sélectionner les cas dont on sait que le codage sera facile.

**2 · Figer le partage.** *Auteur.* Exécuter `partager` pour chaque cas **avant** le début du codage ; le
registre `partage.jsonl` inscrit `{id, usage, date}` et ne se réécrit jamais. Recopier `usage_fige_le`
dans la fiche, et vérifier `usage_fige_le` ≤ `codage.debut`. Le partage précède le codage, pas les faits :
un cas historique a des états anciens et un partage récent.
> *Interdit :* déplacer un cas d'apprentissage vers test, ou l'inverse, une fois l'issue connue.

**3 · Déclarer ce qui fait un signe suffisant.** *Les deux codeurs, séparément.* Avant tout codage,
chacun remplit `codeurs[].signe_suffisant` (`declaration`, `execution` ou `trace`) et `declare_le`, daté
au plus tard au début du codage. Ce champ ne sert pas à excuser un désaccord : il sert à l'**expliquer**.
Deux codeurs qui n'ont pas la même conception du signe suffisant produiront un désaccord systématique, et
l'étude pourra le nommer au lieu de le traiter comme du bruit.
> *Interdit :* remplir ce champ après le premier codage, ou s'attribuer la déclaration de l'autre.

**4 · Coder, premier codeur.** *Codeur 1.* Mode CODER, sources lues et citées, `passage` pour chaque F,
ligne A6 pour chaque voisine, contre-observation et portée pour chaque carte ancrée, `garantie` complète
pour chaque F avec son `support` daté. Puis `valider`. Une fiche invalide se corrige, elle ne se masque
pas.
> *Interdit :* laisser un `?` sur une voisine d'un mot F ; écrire « substantielle mais F maintenu ».

**5 · Exporter vers le second codeur.** *Auteur.* `export-codeur --base … --cas …` produit les faits, les
sources et les dates de disponibilité — **ni état, ni carte, ni force, ni contre-observation**. C'est
exactement la pièce dont A4 a besoin, et elle existe depuis 0.7.8.
> *Interdit :* transmettre la fiche, les notes de codage, un brouillon, une conversation antérieure.

**6 · Coder, second codeur.** *Codeur 2.* Il reçoit les faits et les dates, code selon les règles
courantes, en aveugle du premier codage et sans échanger avec lui. Sa fiche porte son identifiant dans
`codeurs`, avec `independants: true` et `au_moins_un_humain: true`. Ces deux booléens ne sont pas
décoratifs : `bilan` compte les double-codés dessus, et refuse de sortir du mode solo sans eux.
> *Interdit :* toute communication entre les deux codages, y compris « juste pour vérifier une carte ».

**7 · Réunir et dépouiller.** *Une personne qui n'est pas codeur, si possible.* Construire les tables 2×2
par carte et la table groupée. La règle de comptage s'écrit avant le dépouillement : quels états entrent,
quelle carte est « présente », ce qu'on fait d'un état que l'un a codé et l'autre non.
> *Interdit :* supprimer un état du dénominateur parce qu'il est discordant.

**8 · Calculer.** `accord --a … --b … --c … --d …` par carte, puis sur la table groupée. Publier, pour
chaque carte : la table, `pₒ`, `pₑ`, κ et son intervalle, PABAK, π, α, les accords positif et négatif, les
deux taux de manque, l'intervalle de PABAK, `n` et le verdict — plus la version du moteur et l'empreinte
des fiches.
> *Interdit :* publier un κ sans son intervalle, ou un PABAK sans les taux de manque.

**9 · Lire la forme des désaccords.** *Les deux codeurs, ensemble, après le dépouillement.* Par carte :
quels états divergent, sur quel fait, sur quel marqueur, sur quel mot de la définition. La forme compte
plus que l'ampleur. Trois diagnostics utiles, et ils n'ont pas le même remède :

| Forme observée | Diagnostic | Remède |
|---|---|---|
| désaccord concentré sur une carte | marqueur ambigu, ou définition contredite | réviser le marqueur ; la carte retourne en Proposé en attendant |
| désaccord concentré sur un type d'état | lecture du fait, pas de la carte (A5 : annonce contre réalisation) | préciser ce qui compte comme fait, et le dater |
| désaccord diffus | conceptions du signe différentes | comparer les `signe_suffisant` déclarés à l'étape 3 |

> *Interdit :* mettre d'accord les codeurs puis recoder et publier le second codage comme s'il était
> indépendant. Une concession se journalise comme telle ; elle ne devient pas un accord.

**10 · Mesurer la répétabilité.** *Chaque codeur, séparément.* Le même codeur recode à l'aveugle, dans un
ordre tiré, des fiches qu'il a déjà codées, au moins **30 jours** plus tard ; puis
`accord --repetabilite --ecart-jours N`. C'est l'analyse d'accord par attributs de la métrologie —
répétabilité intra-évaluateur — et non un Gage R&R, réservé aux grandeurs continues. En mode solo, c'est
la seule mesure de fiabilité disponible.
> *Interdit :* présenter la répétabilité à la place de l'accord entre codeurs, ou lire une seconde passe
> faite à dix jours.

**11 · Publier la liste et la geler.** *Auteur.* La liste des cartes au verdict `provisoire` ou
`rapportable`, avec son empreinte, se publie **avant l'épisode 1** et ne change plus pendant l'étude. Un
état de V4 qui ancre une carte hors liste n'invalide pas l'épisode : le tiers **retire mécaniquement** le
mot de l'état publié, publie l'état avant et après, et calcule sur ce qui reste. Seul un état devenu nul
fait une abstention.
> *Interdit :* compléter la liste en cours d'étude, ou convertir en abstention un état qui ancre une carte
> hors liste — ce serait laisser au codeur un levier sur le score.

### 3.7 · Les deux accords, et il ne faut pas les confondre

| | Accord **initial** (cette étude) | Accord **prospectif** (pendant V4) |
|---|---|---|
| Quand | avant l'épisode 1 | pendant l'étude, avant la résolution de chaque question |
| Sur quoi | 20 cas de la base, issue connue | 20 % des états de V4, tirés par le tiers |
| Qui code | deux codeurs, dont deux humains par choix | le tiers, contre le codeur de l'auteur |
| Unités | par carte et groupé | **groupé** (de l'ordre de 450 décisions), plus un critère par carte |
| Statistique | κ, PABAK, π, α, intervalle | bootstrap sur les **états**, borne basse de PABAK ≥ 0,67 **et** borne haute du taux de manque ≤ 0,20 |
| Ce qu'il décide | quelles cartes sont admises | si les résultats de V4 peuvent être publiés comme confirmatoires |
| Échec | la carte retourne en Proposé | « codage non reproduit en prospectif » ; aucune conclusion confirmatoire |

Trois précisions sur l'accord prospectif, parce qu'elles sont contre-intuitives.

Il est **groupé** d'abord : à 50 épisodes, le recodage de 20 % ne donne que dix états, très en dessous des
82 décisions nécessaires par carte. La table 2×2 somme donc toutes les décisions carte × strate des états
recodés. Mais un critère groupé peut masquer **une carte fréquente entièrement discordante** : d'où le
critère par carte, qui fait échouer l'accord si une carte atteint cinq ancrages dans le recodage avec un
verdict `insuffisant`.

Il porte sur la **borne basse**, calculée par bootstrap sur les états (2 000 rééchantillons, graine
publique), et non sur l'estimation ponctuelle. Le moteur ne fait pas ce bootstrap : le tiers le fait et
publie son script. La probabilité de passer ce critère est publiée d'avance — avec environ 50 décisions
« présent » et un taux de manque vrai de 10 %, environ 0,77. Le critère est exigeant, et il est censé
l'être.

Il a lieu **avant la résolution** de la question, ou à l'aveugle de son issue. Un recodage fait après
l'issue mesure la connaissance de l'issue, pas la lecture.

### 3.8 · Ce que le résultat autorise à faire

| Résultat | Lecture | Suite |
|---|---|---|
| aucune carte en `insuffisant` | la lecture est reproduite sur le matériel disponible | la liste des cartes `provisoire` et `rapportable` est publiée et gelée ; V4 peut commencer |
| une ou plusieurs cartes < 0,67 | ces cartes ne sont pas admises | elles retournent en Proposé, le marqueur se révise, l'étude se publie quand même ; V4 démarre sans elles |
| cartes `non estimable` (< 5 ancrages) | le matériel ne les a pas rencontrées | elles ne sont ni admises ni refusées ; publier le fait, et le nombre d'états qui les concernaient |
| cartes `sans objet` | personne ne les ancre | résultat, pas échec : une carte que personne n'ancre est sans objet sur cet échantillon |
| accord groupé sous le seuil, **pendant V4** | la lecture n'est pas reproduite en prospectif | aucune conclusion confirmatoire ; libellé « codage non reproduit en prospectif » |
| κ indéfini sur une carte | prévalence nulle | PABAK porte, sous la règle des taux de manque ; publier « indéfini », jamais 0 |

Une seule chose est interdite dans tous les cas : **recommencer sur les mêmes cas jusqu'à passer le
seuil**. Une étude qui reprend son matériel après un échec n'est plus une étude, c'est un ajustement. Si
le marqueur est révisé, la nouvelle mesure se fait sur des cas neufs, ou se publie comme une seconde passe
déclarée sur les mêmes cas — avec la première.

### 3.9 · Ce que l'étude ne peut pas conclure

Six limites, toutes écrites dans le dépôt, et aucune n'est une précaution de style.

1. **Vingt cas ne vérifient pas un seuil à 0,80.** Ils détectent un accord grossier. Un PABAK de 0,70 sur
   vingt décisions ne prouve pas le franchissement de 0,67 : il se publie avec son intervalle.
2. **Les décisions d'un cas ne sont pas indépendantes.** L'intervalle est optimiste ; le nombre de cas
   compte autant que le nombre de décisions.
3. **Un accord sur cas résolus est optimiste.** Le codeur sait où l'histoire va. C'est l'accord prospectif
   qui se lit pour V4, pas celui-ci.
4. **La fiabilité n'est pas la validité.** Une méta-analyse de 96 études d'annotation trouve 74 % d'accord
   moyen dans les études qui mesurent la fiabilité et 86 % dans celles qui produisent un jeu
   d'entraînement ; elle note aussi que des experts et des novices peuvent être chacun fiables et en
   désaccord entre eux. Deux codeurs peuvent donc s'accorder parfaitement sur une classification fausse.
5. **La stabilité n'est pas la validité.** Un modèle de langage peut être stablement faux ; un codeur
   humain aussi. Une répétabilité élevée mesure la constance, pas la justesse.
6. **La répétabilité publiée surestime la stabilité.** Un codeur qui se sait testé est plus constant qu'au
   travail — effet Hawthorne, mesuré sur Galaxy Zoo.

Et une limite qui vaut pour tout le dispositif : **l'étude d'accord ne dit rien de la performance
prédictive.** Elle dit que deux lecteurs lisent la même chose dans les mêmes faits. C'est une condition
nécessaire, jamais suffisante.

### 3.10 · Les six échecs prévisibles, et leur traitement

| Symptôme | Diagnostic | Remède | Ce qu'il ne faut pas faire |
|---|---|---|---|
| PABAK 0,80 et verdict `insuffisant` | un codeur manque plus de 20 % des ancrages de l'autre | regarder **qui** manque quoi ; c'est souvent un désaccord de définition, pas de zèle | publier le PABAK seul : il ne voit pas un codeur qui n'ancre jamais |
| `non estimable` sur plusieurs cartes | moins de 5 ancrages pour chaque codeur | plus de cas, ou déclarer la carte hors du périmètre de cette étude | forcer un ancrage pour faire du nombre |
| κ indéfini | prévalence nulle (`pₑ` = 1) | PABAK porte, avec la règle des taux de manque | écrire κ = 0 |
| accord très élevé, mais `accord négatif` faible | les deux codeurs s'accordent sur les présences et ignorent les absences | compter les absences : sous forte prévalence, c'est la valeur rare, et la règle s'y applique | conclure à une bonne fiabilité |
| désaccord concentré sur une seule carte | marqueur ambigu, ou définition contredite par le fait | réviser le marqueur ; la carte retourne en Proposé | changer de codeur |
| désaccord diffus | conceptions du signe différentes | comparer les `signe_suffisant` datés de l'étape 3 | négocier une définition commune après coup |

Un septième cas mérite d'être nommé, parce qu'il est le plus fréquent dans les projets de ce genre :
**les deux codeurs sont d'accord parce qu'ils ont travaillé ensemble.** L'indépendance n'est pas une
intention, c'est une contrainte matérielle — pas de fiche partagée, pas de conversation, pas de
« relecture rapide ». Aucun moteur ne la vérifie. Elle se publie comme elle se pratique.

### 3.11 · Coût, calendrier, et ce que rien ne raccourcit

Les ordres de grandeur ci-dessous sont des estimations de l'auteur, pas des mesures : elles servent à
décider si le chantier est engagé, pas à planifier une date.

| Poste | Ce qu'il demande | Ce qui peut le réduire |
|---|---|---|
| Coder un cas de strate 7 | lire les sources, écrire une ligne A6 par mot ancré — toutes ses voisines tranchées —, une `garantie` par F, une contre-observation par carte | une carte Documentée et des sources en libre accès ; la strate 7 en a treize |
| 20 cas, deux fois | deux fois le poste précédent, par deux personnes | un second codeur spécialiste du domaine |
| Dépouillement et calcul | une journée, si les tables se construisent proprement | un tableur préparé d'avance, à partir de l'export |
| Répétabilité | deux passes espacées de **30 jours** | rien |
| Accord prospectif | 20 % des états de V4, avant chaque résolution | rien — il est concomitant à l'étude |

Deux durées sont **incompressibles** : les trente jours de la répétabilité, et le fait que l'accord
prospectif ne peut pas précéder les épisodes. Le reste est du travail, et du travail humain.

Ce qui n'est pas dans le tableau, et qui pèse le plus : **l'écriture de la règle de sélection et de la
fiche d'étude avant de coder.** C'est une journée qui paraît perdue et qui décide de la valeur de tout le
reste. Une étude dont la règle de sélection s'écrit après le premier cas ne mesure plus rien.

### 3.12 · La fiche d'étude de l'accord — gabarit

À remplir et à déposer **avant** le premier codage, chez un tiers horodaté. Chaque champ absent rend
l'étude non publiable comme préenregistrée.

| Champ | Contenu attendu |
|---|---|
| version | version du skill et empreinte de `assets/parametres.json` |
| lot | règle de sélection, strate, période, type d'issue, nombre de cas |
| partage | empreinte du registre `partage.jsonl`, date de figeage |
| cartes | les seize cartes, et celles qui sont hors du périmètre de l'étude, avec le motif |
| règle de comptage | ce qui compte comme décision ; traitement d'un état codé par un seul codeur |
| seuils | `kappa_min`, `kappa_rapportable`, `fnr_max`, `accord_min_ancrages` — recopiés, non choisis |
| codeurs | deux identifiants, rôle de chacun, déclaration d'indépendance, `signe_suffisant` et sa date |
| aveuglement | ce que le second codeur reçoit exactement (sortie d'`export-codeur`), et ce qu'il ne reçoit pas |
| dépouilleur | qui construit les tables, et son lien avec les codeurs |
| répétabilité | date prévue de la seconde passe, écart en jours |
| publication | où le rapport et les tables seront publiés, et sous quelle empreinte |
| date limite | au-delà de laquelle l'étude se publie en l'état, avec le nombre de cartes non évaluées |

La fiche de V4 est un autre document, plus lourd : `validation.md` §11.9 en donne les onze champs
(version, banc, horizon, strates, cartes admises, classe de référence, bras, dossier neutre, leurres,
arrêt, tiers). Elle se remplit **après** celui-ci, puisque le champ « cartes admises » est la sortie de
l'étude d'accord.

---

## 4 · Le tiers nommé

### 4.1 · Ce que le protocole lui demande

Un auteur qui code, juge et score ses propres cas reste une source de biais, même avec des sceaux. Le
tiers existe pour cette raison précise, et son rôle est écrit, pas suggéré.

| Ce qu'il fait | Ce qu'il ne fait pas |
|---|---|
| **exécute** le score des épisodes et le test de leurres | ne participe pas à l'écriture des règles ni de la fiche |
| **relit** la fiche d'étude et le §11 avant l'épisode 1, et publie son rapport avec celui du méthodologue | ne réécrit pas le protocole |
| **recode indépendamment** un tirage de 20 % des états de V4 | ne code pas les cas de l'étude d'accord qu'il devra ensuite juger — une double casquette se déclare |
| **tire** les états à recoder, avec la même balise publique que les questions | ne choisit pas la graine |
| **héberge** le modèle à poids ouverts des bras, avec l'empreinte des poids | ne choisit pas le modèle après avoir vu les résultats |
| **prononce** les abstentions, pour un motif de la liste fermée | ne s'abstient pas sur un motif inventé pour l'occasion |
| **publie** son propre rapport | ne signe pas le texte de l'auteur |

**Pourquoi le tiers ne peut pas être un simple auditeur.** Un audit relit un travail fait ; il ne
remplace pas le codage. C'est écrit noir sur blanc : « Un audit seul ne remplace pas ce codage. » La
distinction est ce qui donne au rôle sa valeur — et ce qui le rend coûteux, puisqu'il faut quelqu'un qui
sache coder.

### 4.2 · Ce que son indépendance doit être, et comment elle se publie

Le dispositif repose entièrement sur l'indépendance réelle du tiers, et c'est ce qu'un lecteur jugera en
premier. La fiche publie donc :

- sa **relation à l'auteur** — aucun lien financier, professionnel ou familial, ou leur nature s'il en
  existe ;
- la **façon dont il a été choisi** ;
- une **déclaration d'intérêts signée** ;
- la **date d'engagement**, antérieure à l'épisode 1.

Le choix se fait et se publie **avant** l'épisode 1. Un tiers nommé après les premiers résultats rend
l'étude « exécutée par l'auteur », quel que soit son travail.

### 4.3 · Le matériel qu'il reçoit, et une limite à déclarer

Il reçoit l'**état publié** et le dossier scellé qui le porte — pas les notes de codage, pas le jugement,
pas la prévision. Le protocole impose un ordre strict : l'état est codé et son empreinte publiée ; le
contrôle de la liste des cartes admises s'applique à cet état ; **le tiers calcule p** ; puis le scellement
intervient, obligatoire. Un p calculé ne se retire pas, l'état ne se recode pas.

Une limite que le protocole déclare lui-même : **« le codeur ne lance jamais le calcul » est
invérifiable.** Le moteur est public, et une exécution privée ne laisse pas de trace. Deux options, et la
fiche dit laquelle est retenue : un codeur qui n'a pas l'environnement du moteur, ou la déclaration de la
limite dans la publication. La seconde est plus honnête, la première plus solide.

### 4.4 · Sans tiers

Rien n'interdit de commencer. Mais un résultat sans tiers se publie **« exécuté par l'auteur »**, et cette
mention suffit à un lecteur pour classer le travail. Pour une première étude dont l'enjeu est justement de
montrer qu'on sait mesurer, c'est un mauvais échange : le coût du tiers est de quelques semaines de sa
part, le coût de son absence est le statut de tout le reste.

---

## 5 · La relecture par un méthodologue extérieur

### 5.1 · Ce qui est demandé, et pourquoi ce n'est pas la même chose qu'un audit interne

Le dépôt a été relu neuf fois, par le même lecteur, avec la même grille. Ces relectures ont fermé une
quarantaine de marges de décision, et le relecteur lui-même écrit que ce n'est pas une évaluation
indépendante. C'est pourquoi la règle existe, et elle est nette :

> la fiche et le §11 sont relus par **un biostatisticien ou un méthodologue qui n'a pas participé à leur
> écriture**, et par le tiers désigné ; leurs rapports se publient avec la fiche. Cette relecture externe
> est une condition de l'épisode 1, au même titre que l'étude d'accord.

Deux choses à retenir. Ce n'est pas un audit de code ni d'intégrité — l'audit existe et il est automatique.
C'est une relecture de **dispositif** : est-ce que ce test peut répondre à la question posée, et le
pourra-t-il encore après qu'on aura vu les données ?

### 5.2 · La grille, en douze questions

À poser telles quelles. Chacune correspond à une décision que le dépôt a prise, et chacune peut recevoir
un « non » argumenté — c'est ce qu'on demande au relecteur.

| # | Question | Ce qu'une réponse « non » coûterait |
|---|---|---|
| 1 | L'**estimande** est-il défini avant la mesure, et est-ce un différentiel de Brier par épisode, entre le moteur et un comparateur fixé au même horizon ? | on ne saurait pas ce que le chiffre mesure |
| 2 | Les **issues** du test sont-elles écrites, exhaustives et lisibles dans le code — gain, non-supériorité, nuisance, non établi ? | une issue pourrait se découvrir après les résultats |
| 3 | L'erreur est-elle contrôlée **par énoncé**, et les énoncés se publient-ils toujours ensemble, y compris ceux qui échouent ? | plusieurs occasions d'affirmer à tort, dont on ne publierait que la réussie |
| 4 | L'**effectif** est-il justifié par une formule figée, et son résultat recalculé **une seule fois** après vingt épisodes ? | l'effectif deviendrait un choix post hoc |
| 5 | La **dépendance entre épisodes** est-elle traitée — et que se passe-t-il au-delà du seuil d'autocorrélation de 0,3 ? | deux tests permissifs, l'équivalence la première |
| 6 | Les décisions d'un même cas sont-elles traitées comme **non indépendantes** — bootstrap par état, intervalle déclaré optimiste ? | un accord groupé surévalué |
| 7 | Le **critère d'accord** est-il lisible avant la mesure, et son effectif est-il suffisant pour le seuil qu'il prétend vérifier (82 décisions pour la borne, 250 pour 0,80) ? | une liste de cartes admises sur du bruit |
| 8 | La **sélection des questions** est-elle scellée avant lecture, avec une seule exclusion mécanique admise ? | un sous-ensemble choisi par l'outil |
| 9 | Les **abstentions** sont-elles repliées sur la fréquence de base, et le taux plafonné (40 % par défaut) ? | un score calculé sur les seules questions où l'alphabet s'exprime |
| 10 | Les **bras d'un modèle** sont-ils figés — version, consigne et son empreinte, température, cinq exécutions, médiane, écrêtage ? | un bras qui peut changer avant la fin |
| 11 | Le **tiers** est-il nommé avant, indépendant, et son rôle écrit ? Le **dossier neutre** est-il produit mécaniquement, avec un gabarit gelé et son empreinte publiée ? | la conclusion se lirait « exécutée par l'auteur » |
| 12 | Ce que la **conclusion négative n'exclut pas** est-il écrit en clair — un apport inférieur à 2,5 points ? | une phrase vraie lue comme une phrase plus forte qu'elle n'est |

Trois questions supplémentaires, si le relecteur en a le temps.

- Le **seuil de 2,5 points** est-il justifié autrement que par sa commodité ? Le dépôt répond : c'est 10 %
  d'un Brier de 0,25, et un seuil de 1 point demanderait environ 620 épisodes en non-supériorité et 860 en
  équivalence.
- La **zone grise** est-elle publiée ? Un apport vrai entre 2 et 4,5 points finira le plus souvent « non
  établi ». Ce n'est pas un défaut, c'est le domaine du test, et il doit être écrit avec la fiche.
- Le **tiers** pourrait-il, en pratique, exécuter ce qui lui est demandé — accès au banc, hébergement du
  modèle à poids ouverts, compétence de codage ? Une condition non réalisable n'est pas une condition.

### 5.3 · Ce qu'il ne fait pas

- Il ne réécrit pas le protocole. Un relecteur qui réécrit devient co-auteur, et la relecture perd son
  statut.
- Il ne décide pas d'un seuil après avoir vu des résultats. Avant l'épisode 1, un seuil peut encore
  changer — c'est le moment. Après, non.
- Il ne valide pas l'instrument. Un avis favorable dit que le dispositif est correctement construit, pas
  que l'alphabet prédit.
- Il ne remplace pas le tiers. Ce sont deux fonctions distinctes : l'un juge le dispositif, l'autre
  exécute la mesure.

### 5.4 · Le livrable, et ce qu'on en fait

Un **rapport daté et signé**, publié avec la fiche d'étude et le rapport du tiers. Rien n'oblige à ce
qu'il soit long : une page qui répond aux douze questions, avec les points bloquants séparés des
suggestions, suffit.

Trois issues, et elles n'ont pas le même effet.

| Constat | Effet | Ce qui se passe ensuite |
|---|---|---|
| défaut de **texte** (une règle contredit une autre, un libellé est faux) | correction | version datée, `CHANGELOG` conserve l'entrée fautive ; **aucune nouvelle étude** |
| défaut de **valeur gelée**, constaté **avant** l'épisode 1 | la valeur peut changer | datée, publiée, l'ancienne valeur déclarée, la fiche re-scellée ; rien n'a encore été mesuré |
| défaut de **valeur gelée**, constaté **après** l'épisode 1 | la valeur ne change plus | **nouvelle étude**, sur des épisodes neufs |

La deuxième ligne est la plus utile, et la plus fragile. Avant le premier épisode, tout est encore une
décision d'auteur, et une relecture qui trouve une erreur rend service. C'est exactement pour cela que la
relecture est une **condition** de l'épisode 1 et non une formalité de publication.

---

## 6 · La porte de l'épisode 1 — liste de contrôle

Une seule page, à cocher avant de journaliser quoi que ce soit. Chaque ligne renvoie à la preuve qui la
rend vérifiable par un lecteur qui n'était pas là.

| # | Condition | Preuve attendue | Qui signe | État |
|---|---|---|---|---|
| 1 | Cas réels actifs codés sous les règles courantes | `moteur.py bilan` : étape 2 non vide | codeur 1 | **non fait** |
| 2 | Étude d'accord faite sur ≥ 20 cas et ≥ 20 % de la strate | tables 2×2 par carte, verdicts, intervalles, `n` | dépouilleur | **non fait** |
| 3 | Liste des cartes admises publiée et gelée | liste + empreinte, datée avant l'épisode 1 | auteur | **non fait** |
| 4 | Tiers nommé et publié | nom, rôle, relation à l'auteur, choix, déclaration d'intérêts, date | tiers | **non fait** |
| 5 | Relecture par un méthodologue extérieur publiée | rapport daté, signé, joint à la fiche | méthodologue | **non fait** |
| 6 | Fiche d'étude horodatée chez un tiers | les onze champs remplis, empreinte de `parametres.json` | auteur + tiers | **non fait** |
| 7 | Banc de questions, règle de tirage, graine publique | règle publiée, graine postérieure à l'engagement | auteur | **non fait** |
| 8 | Classe de référence et fréquences de base publiées | règle et valeurs, datées avant l'épisode 1 | auteur | **non fait** |
| 9 | Dossier neutre produit mécaniquement, gabarit gelé | gabarit + empreinte publiés | tiers | **non fait** |
| 10 | Rédacteur des leurres et juges désignés | consigne de réécriture, noms, contrôle positif des juges (9/10) | tiers | **non fait** |
| 11 | Modèle à poids ouverts nommé, version figée, hébergé par le tiers | nom, version, empreinte des poids | tiers | **non fait** |
| 12 | Date limite et plafond d'effectif déclarés | date, plafond (300 épisodes par défaut) | auteur | **non fait** |
| 13 | Taille du tirage prospectif et script de bootstrap arrêtés | 20 % des états, 2 000 rééchantillons, graine | tiers | **non fait** |

Deux lignes méritent un commentaire, parce qu'elles sont les plus souvent comprises de travers.

**La ligne 3 n'est pas une formalité.** La liste des cartes admises est le seul endroit où l'étude
d'accord se traduit en contrainte opérationnelle. Sans elle, un épisode peut ancrer n'importe quelle carte
et le score devient incomparable d'un épisode à l'autre.

**La ligne 12 n'est pas de la prudence administrative.** Une étude sans date limite est une étude qui
continue jusqu'à ce qu'elle trouve quelque chose. Le plafond de 300 épisodes existe pour la même raison :
au-delà, l'incertitude sur σ̂ rend l'effectif ininterprétable.

---

## 7 · Ce qui reste après la porte

Dans l'ordre, et sans détailler — ce document s'arrête là où le protocole reprend la main.

1. **V4, deux énoncés séparés.** C (« les cartes apportent au moins 2,5 points », contre l'inertie de
   strate) et A (« l'appareil apporte au moins 2,5 points », contre un modèle qui lit les mêmes faits et
   les mêmes fréquences). Chacun son α, chacun sa puissance, tous deux publiés ensemble. Point de lecture :
   171 épisodes à σ(d) = 0,10.
2. **Le test de leurres.** Quarante situations, une lecture réelle et un leurre à cartes tirées, deux
   juges, critère de 26 sur 40. Un échec se publie : « lectures non distinguées d'un leurre à cartes
   permutées ».
3. **Le résultat nul, s'il est nul.** C'est une contribution, et le dépôt le dit depuis longtemps.
4. **La strate pilote, complétée.** Un Proposé (PÉRIODICITÉ), deux Vides (CROISSANCE, RÉSONANCE) : du
   temps de lecture, pas des données.
5. **Les fréquences externes** (étape 4), qui font passer les prévisions de ρ4 à ρ3.
6. **Les versions 0.8, 0.9, 1.0** du dépôt analysé : structure, épreuve, grammaire. La dernière attend un
   rédacteur indépendant de la matrice.
7. **L'étiquetage de cette révision** (`v0.7.51`) et la vérification du manifeste après envoi — puis
   la prochaine révision, quand un premier cas réel sera actif.

---

## 8 · Conventions de travail

Dix règles, dans l'ordre où elles se rencontrent.

1. **Ne pas changer un seuil gelé.** Ils sont datés, écrits avant les données, et une valeur changée après
   l'épisode 1 ouvre une nouvelle étude sur des épisodes neufs.
2. **Chaque chiffre a sa commande.** Un chiffre recopié d'un document antérieur se marque comme recopié.
3. **Une correction ne réécrit pas l'histoire.** Le journal conserve l'entrée fautive et nomme ce qui a
   changé, avec le motif.
4. **Le second codeur ne voit jamais le premier codage.** Ni la fiche, ni les notes, ni une conversation.
5. **Ce qui n'est pas scellé n'existe pas.** Un état sans empreinte publiée avant le calcul ne compte pas
   comme préenregistré.
6. **La troisième personne.** On écrit « le dépôt », « l'auteur », « le codeur » — jamais « je », sauf
   dans un journal de bord daté.
7. **Un cas non vérifié est une archive.** `sources_verifiees: false` et un motif ; il sort des calculs et
   reste comme trace.
8. **Le moteur est public, et ses résultats sont reproductibles.** Un résultat qu'on ne peut pas rejouer
   n'est pas un résultat.
9. **Une construction ad hoc est une dette.** Une carte, une strate ou une règle inventée en cours de
   codage s'inscrit au journal des lacunes (`rabbits.jsonl`) ; trois occurrences indépendantes ouvrent une
   procédure d'admission.
10. **Ce qui est publié est daté.** Une date, une version, une empreinte. Sans les trois, un lecteur ne
    peut pas savoir ce qu'il lit.

---

## Annexe A · Les commandes citées ici

Données pour un shell POSIX (`python3`) ; sous Windows, `python` suffit.

| Commande | Ce qu'elle fait | Où elle est utilisée |
|---|---|---|
| `moteur.py audit` | intégrité du paquet : manifeste, paramètres, schémas, renvois | §1.4 |
| `moteur.py autotest` | 155 tests de régression | §1.4 |
| `moteur.py bilan` | avancement mesuré sur la feuille de route, mode solo compris | §1.4, §3.2 |
| `moteur.py partager --id …` | inscrit l'usage et la date au registre, avant codage | §3.6, étape 2 |
| `moteur.py export-codeur --base … --cas …` | faits, sources et dates, sans état ni carte | §3.6, étape 5 |
| `moteur.py valider …` | forme de la fiche, voisines, garanties, passages, partage | §3.6, étape 4 |
| `moteur.py accord --a … --b … --c … --d …` | table 2×2, κ, PABAK, π, α, taux de manque, intervalle, verdict | §3.4, §3.6 |
| `moteur.py accord --repetabilite --ecart-jours N` | même codeur, deux passes espacées | §3.6, étape 10 |
| `moteur.py accord --llm` | deux exécutions d'un modèle, publiées séparément | §3.1 |
| `moteur.py dossier --fichier …` | valide le dossier de lecture et rend son sceau | §4.3 |
| `moteur.py calculer --dossier …` | calcule p depuis un dossier scellé | §4.3 |
| `moteur.py scorer …` | score par épisode, `v4.decision`, couverture, repli | §7 |
| `moteur.py parametres` | table exhaustive des paramètres, générée depuis le JSON | §3.4 |

Deux remarques d'environnement. `audit` refuse un fichier non répertorié au manifeste : un fichier de
travail déposé dans le dossier du skill fait échouer l'audit, et c'est voulu. Et `accord` n'a besoin que
de quatre entiers : la table se construit à la main ou par script, mais elle doit être publiée telle
quelle, avec `n`.

---

## Annexe B · Lexique pour un collaborateur non méthodologue

Les mots du protocole qui ne veulent pas dire ce qu'ils ont l'air de dire.

| Terme | Ce qu'il désigne ici | Le piège |
|---|---|---|
| **carte** | une des seize structures (SEUIL, RÉSEAU, POLARITÉ…) | ce n'est pas une catégorie thématique, c'est une structure nommée |
| **strate** | une des treize disciplines, rattachée à une taxonomie existante | ce n'est pas un niveau d'analyse, c'est un domaine |
| **mot** | une carte ancrée dans une strate, avec sa force : `SEUIL@7[F]` | la force n'est pas une intensité |
| **F / f** | qualité de l'ancrage : Fort ou Faible | F ne veut pas dire « probable » ; ce n'est pas un modalisateur |
| **état** | l'ensemble des mots ancrés à une date, dans une fenêtre | un état n'est pas un résumé de la situation, c'est ce qui s'ancre |
| **décision** | l'unité de mesure de l'accord : pour une carte et un état, ce qu'un codeur a tranché — ancrée ou non | deux décisions, une par codeur, forment une case de la table 2×2 ; l'unité n'est pas le cas |
| **p** | fréquence conditionnelle expérimentale, jamais une probabilité calibrée | le niveau ρ dit la provenance, pas la fiabilité |
| **ρ** | niveau de provenance d'une prévision, de ρ0 (30 cas) à ρ4 (intuition) | ρ0 n'est pas « fiable » ; c'est « appuyé sur des cas » |
| **homologue** | un cas passé dont l'état structurel ressemble à l'état courant | la proximité n'est pas une identité causale |
| **placebo** | le même calcul, avec des cas tirés au hasard au lieu des homologues | ce n'est pas un placebo de cartes ; il garde les λ |
| **inertie de strate** | le même tirage de cas, sans les multiplicateurs des cartes | c'est le comparateur des cartes ; `p_sans_cartes` en est un autre |
| **κ** | accord corrigé du hasard attendu | il s'effondre quand le code est rare ; ce n'est pas lui qui décide |
| **PABAK** | accord observé ramené à une échelle symétrique | il ne voit pas un codeur qui n'ancre jamais |
| **taux de manque** | ce qu'un codeur rate des ancrages de l'autre | deux taux, jamais un : aucun codeur n'est la référence |
| **prévalence** | fréquence du code dans l'échantillon | au-delà de 0,5, la valeur rare devient l'absence, et la règle s'y applique |
| **dossier scellé** | la lecture complète, empreintée avant le calcul | il fige la lecture, pas le jugement |
| **épisode** | deux questions de même date de résolution et même événement sous-jacent | l'unité du score, pas la question |
| **Brier** | erreur quadratique d'une probabilité | borné : 0,25 est la valeur d'une prévision à 50 % |
| **e-processus** | un test lisible à tout instant sans gonfler α | il est moins puissant qu'un test à un regard, et c'est son prix |
| **non-supériorité** | « l'écart ne dépasse pas 2,5 points en défaveur » | ce n'est pas « il n'y a pas d'apport » |
| **nuisance** | « l'alphabet dégrade de plus de 2,5 points » | c'est un énoncé séparé, et un résultat publiable |

---

## Ce que ce document ne remplace pas

Il ne remplace ni la note, qui juge, ni le dépôt, qui fait foi. Il ne dispense pas de lire
`references/validation.md` §11 avant de toucher à V4 : c'est le seul endroit où les règles de décision
sont écrites en entier, avec leurs corrections successives et les raisons de chaque correction. Et il ne
transforme pas une étude d'accord en validation : elle dit que deux lecteurs lisent la même chose, ce qui
est la condition d'un résultat, pas le résultat.
