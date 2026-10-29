# Lire le langage, prévoir l'événement

### Ce que la science a déjà essayé — et où se situe l'Alphabet situationnel

**Note de synthèse · version 0.7.4 · 29 octobre 2026**

Dépôt analysé : `Othman-Benbrahim/alphabet-situationnel` · version 0.7.4 · licence MIT
Vérifications exécutées le 29/10/2026 : `audit` conforme · **115 autotests** · `bilan` de la feuille de route

> **Comment lire cette note.** Elle porte sur l'état du dépôt au 29 octobre 2026, après les versions
> 0.7.3 et 0.7.4. Elle suit le plan de la note du 28 octobre (état des lieux, fonctionnement, axiome,
> littérature, comparaison, bilan, recommandations) et signale en annexe B ce qui a changé entre les
> deux. Les chiffres de démonstration viennent d'une base **entièrement fictive** : ils illustrent une
> mécanique, jamais une performance. Aucune performance prédictive n'est acquise.

---

## L'essentiel en sept points

1. **Un protocole complet, toujours zéro cas actif.** 16 cartes, 13 strates, 208 cases, 66 transitions,
   50 fichiers, 49 au manifeste. L'audit passe, les 115 autotests passent ; l'audit vérifie la forme et
   le recoupement interne, pas la vérité du contenu.
2. **Les versions 0.7.3 et 0.7.4 ont changé la nature de l'objet.** La lecture qui produit le chiffre
   est désormais contrôlée par le moteur **avant** lui, scellée, et exigée pour compter dans le jalon de
   validation. Ce n'est pas une fonctionnalité de plus : c'est la théorie de la preuve du dépôt qui
   devient exécutable dans le seul mode où elle était absente.
3. **L'axiome reste plus fort que celui de CAMEO.** CAMEO dit « les actes se suivent » ; l'alphabet dit
   « les structures se ressemblent, donc les avenirs se ressemblent ». C'est une hypothèse d'homologie,
   pas une chaîne de Markov.
4. **La science a testé quatre familles** — coder les actes (CAMEO, GDELT, ICEWS), compter les mots ou
   les thèmes (Chadefaux, Mueller & Rauh, EPU), lire le ton et le changement (Tetlock, Lazy Prices),
   confier le texte au modèle (LLM). Toutes marchent sur le fréquent et le proche ; presque toutes
   échouent sur la rupture rare.
5. **Les deux résultats les plus proches de la méthode sont ambigus.** La similarité de séquences
   distingue bien la paix, mal l'escalade (D'Orazio & Yonamine, 2015) ; l'autorégression égale ou bat
   souvent les modèles structurels (Chadefaux & Schincariol, 2025).
6. **Nouveau, et le plus important : le dépôt peut désormais mesurer sa propre hypothèse.** Un placebo
   d'homologie tire au hasard autant de cas que la classe retenue et refait le calcul. Sur la base de
   démonstration — fictive — les cartes déplacent la probabilité de **+10,0 points** sur l'événement
   phare, mais le choix des cas n'en apporte que **+1,8** ; sur cinq événements, **+0,9** et **+0,7**.
   Autrement dit : l'écart à l'inertie vient du multiplicateur a priori, non de l'analogie. Ce n'est pas
   un résultat sur l'axiome, c'est un instrument qui fonctionne — et qui, pour la première fois, pourrait
   le contredire.
7. **Le prochain pas n'est pas une 17<sup>e</sup> carte.** C'est un second codeur, vingt cas, et un test
   contre l'inertie — auquel s'ajoute maintenant le placebo, qui doit précéder la vue des résultats.

---

## 01 · État des lieux

> Ce qu'est le dépôt, ce qu'il contient, ce qu'il sait faire — et ce qu'il ne sait pas encore.

### 1.1 · Un protocole, pas un article

L'Alphabet situationnel n'est ni un modèle statistique ni un essai : c'est un **protocole de lecture et
de prévision**, écrit comme un skill pour modèle de langue, doublé d'un moteur Python autonome
(bibliothèque standard seulement, 251 Ko, 3 494 lignes). Le paquet compte 50 fichiers : le moteur, 19
références principales, 13 fichiers d'équivalents (un par strate), des bases JSONL, un journal
d'exemple, un dossier de lecture d'exemple, un manifeste SHA-256 de 49 fichiers et une intégration
continue qui rejoue l'audit et les tests à chaque push.

```
moteur.py audit    → conforme — 208 statuts, paramètres exhaustifs (chacun référencé par le code),
                      JSONL et dossier d'exemple validés, manifeste 49 fichiers, matrice et inerties,
                      131 renvois §, voisines A6, incompatibilités G6, schéma de fiche validé
moteur.py autotest → 115 tests
moteur.py bilan    → 0 cas actif · 13/16 équivalents en strate 7 · aucun journal · V4 non commencé
```

Cette solidité formelle est réelle, et rare pour un projet de recherche indépendant. Mais il faut lire
la phrase jusqu'au bout : l'audit contrôle « la forme et le recoupement interne, pas la justesse du
contenu ni la certification empirique ». C'est le dépôt lui-même qui le dit, et le `SKILL.md` ajoute
depuis 0.7.3 un tableau qui nomme, ligne par ligne, ce que le moteur contrôle et ce qu'il laisse au
jugement.

### 1.2 · Quatre modes, sept couches

Le protocole sépare radicalement quatre usages. C'est une des bonnes idées du dépôt : on peut lire sans
prévoir, et coder sans scorer.

| Mode | Demande typique | Couches | Sortie |
|---|---|---|---|
| **LIRE** | « lis cette situation » | 0–2 | état daté, preuves, alternatives, questions qui départagent — sans prévision |
| **PRÉVOIR** | « que peut-il se passer d'ici… » | 0–5 + journal | événements définis, résultats du moteur ou non-estimation motivée |
| **CODER** | « code ce cas historique » | 0–3 | fiche validée ou archive à revoir, explicitement exclue |
| **SCORER** | « voici ce qui s'est produit » | 6 | journal contrôlé, scores, exclusions, épisodes comparables |

Les sept couches forment une chaîne : ontologie → alphabet → grammaire → base de cas → graphe de
transitions → simulation → validation. Chaque couche a ses règles numérotées (O, A, G, B, T, S, V) ;
une règle qui contredit l'un des neuf principes de la constitution est nulle et doit être corrigée, pas
appliquée.

Ce que les versions récentes ont déplacé, mode par mode :

| Mode | Avant 0.7.3 | Depuis 0.7.4 |
|---|---|---|
| LIRE | sortie libre, contrôlée par relecture humaine | inchangé — le mode reste sans calcul |
| PRÉVOIR | A6, A7, garantie, passage, questions : obligations **narratives**, sans contrôle ni trace | dossier de lecture validé **avant** le chiffre, sceau publié, placebo et deux bandes de sensibilité dans la sortie |
| CODER | fiche validée par `valider_base` | idem, plus `usage_fige_le` et `codage.debut` recoupés avec un registre daté |
| SCORER | Brier, comparateurs, abstentions, difficulté | idem, plus `p_placebo`, `apport_homologie`, et l'exigence de `preuve_dossier` pour compter dans V4 |

### 1.3 · Seize cartes, treize strates

Les cartes sont les « lettres » de l'alphabet. Chacune est une structure mathématique nommée, pas une
métaphore : c'est ce qui la rend, en principe, falsifiable.

`⊥ SEUIL` (hystérésis, bistabilité) · `⊗ RÉCIPROCITÉ` (jeux répétés, donnant-donnant) ·
`↻ PÉRIODICITÉ` (orbites, cycles limites) · `↺ RÉCURSIVITÉ` (points fixes auto-référents) ·
`⊙ ÉMERGENCE` (auto-organisation) · `✦ HIÉRARCHIE` (ordres partiels) · `⊛ RÉSEAU` (graphes, ponts,
trous) · `⥀ POLARITÉ` (involution, groupe ℤ₂) · `Ø INCERTITUDE` (distribution sur états) ·
`⊘ CONTRAINTE` (ensemble admissible) · `◯ PROPORTION` (ratios, changement d'échelle) ·
`∿ TRANSFORMATION` (homotopies, invariant) · `◊ TRACE·MÉMOIRE` (dépendance au chemin) ·
`▲ CROISSANCE` (exponentielle, logistique) · `⟶ COMMUNAUTÉ` (biens publics à n joueurs) ·
`✶ RÉSONANCE` (oscillateurs couplés)

Les strates sont volontairement éloignées les unes des autres : 1 Matière · 2 Vivant · 3 Psyché ·
4 Relations · 5 Organisations · 6 Économie · 7 Géopolitique · 8 Droit · 9 Culture · 10 Technique ·
11 Climat · 12 Histoire longue · 13 Politique intérieure. Le principe P1 est explicite : cette distance
sert à tester la portée descriptive d'une carte ; elle ne démontre pas que ses dynamiques prédictives se
transportent d'une strate à l'autre.

**Une collision de notation, désormais explicitée.** Deux échelles portent les mêmes lettres : le `F`/`f`
d'un mot est la **confiance de l'ancrage**, le `F`/`M`/`f` d'une case de matrice est la **force postulée
d'une transition**. Seule la seconde produit un multiplicateur λ. Le glossaire distinguait déjà les deux
notions ; ce qui manquait, et que 0.7.3 a écrit dans `SKILL.md` et `graphe.md`, est la conséquence : un
ancrage F ne rend pas un λ plus fort.

### 1.4 · Le moteur : deux formules, quatre garde-fous

Tout chiffre sort du moteur ; le modèle choisit les événements et contrôle le sens des preuves.

```
// 1. a priori : fréquence de base f, multiplicateurs des cartes présentes
p₀ = f × LR / (1 − f + f × LR)      avec LR = produit des λ, plafonné à 10

// 2. révision bayésienne par les cas homologues
P  = (n_E + k × p₀) / (n_A + k)     k = 2
```

Les multiplicateurs sont des hypothèses de travail, pas des rapports de vraisemblance mesurés :
λ = 3,0 pour une transition forte, 1,8 moyenne, 1,2 faible. La fréquence par défaut est de 5 % sur trois
mois ; les inerties vont de 0,40 (INCERTITUDE) à 0,97 (SEUIL). La fréquence de base est lissée vers la
référence par `k₀ = 20`, et n'est dite **ancrée** qu'au-delà d'un effectif pondéré de 10 cas.

Quatre garde-fous entourent ce calcul, et c'est là que le dépôt est le plus original :

| Garde-fou | Ce qu'il mesure | Depuis |
|---|---|---|
| **Comparateur inertiel** (`p_sans_cartes`) | ce que les cartes ajoutent au statu quo | 0.5.0 |
| **Bande de modèle** | six variantes de λ, inerties, fréquence par défaut | 0.6.0 |
| **Bande de classe** | huit variantes du choix des cas : Jaccard ± 0,1, k et k₀ × ½ et × 2, demi-vie × ½ et × 2 | **0.7.3** |
| **Placebo d'homologie** (`p_placebo`) | ce que la sélection des homologues ajoute à des cas tirés au hasard, en même nombre | **0.7.4** |

S'y ajoutent deux diagnostics : la **fragilité de niveau** (0.7.3), qui publie l'écart entre les `p`
calculés sur chaque niveau d'homologie non vide — le seuil `c_min_rho1 = 3` décide seul du niveau
retenu — et la **sonde de force**, qui chiffre ce que F/f change (uniquement par la sélection des
homologues).

```
Sortie d'une démonstration — base fictive, --demo

État               [2026-09 | 3 mois] POLARITÉ@7[F] + CONTRAINTE@6[F]
Événement          SEUIL@7 apparait
Probabilité        22,0 % [5,2–43,1]        intervalle bêta conditionnel, approximatif
Sans les cartes    12,1 %                   comparateur inertiel
Apport des cartes  +10,0 points
Placebo            20,2 % (200 tirages de 10 cas parmi 28 ; 90 % entre 10 et 34 %)
Apport de l'homologie  +1,8 points
Sensibilité modèle 19–28 % · classe 21–23 % (stable) · force +0,7 pt
Niveau             ρ1 · H1 · 10 cas · n_A 4,8 · part de l'a priori dans f 54 %
Barreau            A (association)
```

La base est entièrement fictive : ces chiffres illustrent la mécanique, ils ne constituent ni une
prévision réelle ni une preuve de calibration. Le moteur l'écrit lui-même dans ses drapeaux.

**Comment lire la ligne « placebo ».** Elle compare le chiffre obtenu avec les cas choisis par le motif
structurel à celui obtenu avec autant de cas tirés au hasard dans la même strate et la même fenêtre, sous
le même a priori. Trois lectures sont possibles, et elles n'ont pas la même valeur pour l'axiome :

- **apport proche de zéro** : l'homologie ne fait rien ; le chiffre vient de l'a priori et des cas de la
  strate en général. C'est la lecture défavorable, et la plus probable tant que la base est petite ;
- **apport négatif** : la sélection des cas dégrade par rapport au hasard. C'est un résultat, et une
  raison de réviser les marqueurs de la carte avant d'aller plus loin ;
- **apport positif franc** : l'hypothèse d'homologie mérite alors le test à l'aveugle. C'est la seule
  lecture qui la soutienne, et c'est celle qu'il faut mériter.

### 1.5 · La dette empirique, en une barre

Les 16 cartes × 13 strates font 208 cases. Voici comment elles sont remplies.

| Statut | Nombre | Part |
|---|---|---|
| Attesté | 0 | 0 % |
| Documenté | 13 | 6,25 % |
| Proposé | 182 | 87,5 % |
| Vide | 13 | 6,25 % |
| Hors domaine | 0 | 0 % |

Les 13 « Documenté » sont tous en strate 7 (géopolitique), la strate pilote. Aucune case n'est
« Attesté » : aucune n'a été recodée sur un cas réel sous les règles courantes. Et le bilan est sans
ambiguïté :

```
Étape 2 · cas réels          : 0 actifs · 0 propositions · 4 archives
Étape 3 · strate pilote      : 13/16 Documentés · 0 strate complète · 0/13 cases Vides closes
Étape 4 · références externes: aucun fichier fourni
Étape 5 · base réelle        : aucun cas actif · κ non calculé
Test à l'aveugle             : aucun journal fourni (0/50)
```

C'est l'état exact : un cadre complet, une base vide. Les quatre cas réels existants ont été archivés
(décision d'auteur, 0.6.8) parce qu'ils avaient été codés après leur issue, sous des règles antérieures.
Ils restent comme trace, exclus de tout calcul.

### 1.6 · Ce que dit la matrice

La matrice de transitions contient 66 liens sur 240 possibles (16 × 15). Trois seulement sont forts
(F), 27 moyens (M), 36 faibles (f). Autrement dit : la théorie interne de l'alphabet est majoritairement
faite de liens faibles.

Les trois seuls liens forts : **SEUIL → TRACE**, **ÉMERGENCE → TRACE**, **CROISSANCE → CONTRAINTE**.
Autrement dit : « un seuil laisse une trace », « une émergence laisse une trace », « une croissance
rencontre une limite ». Ce sont les affirmations les plus solides — et les plus générales.

| Observation | Mesure |
|---|---|
| SEUIL comme centre de gravité | 14 des 66 liens entrants (21 %), poids cumulé **21,6** ; CONTRAINTE second à **9,0** |
| Liens forts | 3 sur 66 (4,5 %) |
| Liens ajustés sur des données | 0 |

Trois conséquences. **Premièrement**, la théorie interne donne à SEUIL un poids d'entrée très supérieur :
le moteur sera porté à surestimer les seuils — et le dépôt avertit déjà de « surveiller la
sur-prédiction de SEUIL ». Ce n'est pas une intuition : c'est inscrit dans la matrice. **Deuxièmement**,
les trois liens forts sont des quasi-tautologies : ils sont les plus assurés et les moins informatifs.
**Troisièmement**, la matrice est une théorie qualitative, pas un objet estimé : le graphe n'est pas
appris, il est postulé.

Un contrôle de calibration spécifique à SEUIL reste donc nécessaire, distinct du Brier global : sur les
50 épisodes du test à l'aveugle, comparer la fréquence observée des seuils à la fréquence prédite. Un
modèle qui sur-prédit les ruptures peut avoir un Brier correct et une lecture fausse.

**Ce que 0.7.3 ajoute à cette section.** La fragilité de niveau chiffre ce que le § 1.4 appelait un
« compromis raisonnable ». Mesuré sur une base synthétique de 2 cas stricts positifs et 3 cas plus larges
négatifs : le seuil `c_min_rho1 = 3` écarte les deux cas H1 parfaitement comparables, retient les cinq
cas H1.5, et `p` passe de **53 % à 33 %**. Vingt points d'écart, décidés par un compte de cas. Le moteur
publie désormais cet écart ; avant 0.7.3, il ne publiait que les effectifs.

### 1.7 · Où en est le dépôt

| Étape | Objet | État mesuré |
|---|---|---|
| 0 | Installer la version courante | **fait** — 0.7.4 |
| 1 | Trois décisions d'auteur | **prises** — strate 12 conservée · cartes à agents universelles · MIT |
| 2 | Premiers cas réels sous les règles courantes | **0 actif** — 4 archives exclues |
| 3 | Sourcer une strate pilote | **13/16** — strate 7, 0 strate complète |
| 4 | Bibliothèque de fréquences externes | **aucune** |
| 5 | Base réelle et second codeur | **aucune** — κ non calculé |
| — | Test à l'aveugle (jalon V4) | **non commencé** — 0/50 |

Depuis le 29 octobre 2026, quatre décisions d'auteur sont appliquées (sceau de dossier exigé pour V4,
partage apprentissage/test daté, placebo d'homologie, plancher de recherche A7). Une cinquième est
réservée à une version séparée : l'atténuation des multiplicateurs par la qualité de l'ancrage. Le
diagnostic du dépôt reste donc juste, et il faut lui rendre cet hommage : le cadre est complet, ce qui
manque est empirique ou relève de l'auteur.

Le risque n'est pas l'erreur ; c'est que le protocole reste indéfiniment un chef-d'œuvre de méthode sans
jamais rencontrer un cas.

---

## 02 · Comment il fonctionne

> Sept gestes, un exemple, et un lexique. L'objectif est de pouvoir expliquer le dépôt à quelqu'un qui
> n'a jamais lu une seule référence.

### 2.1 · L'exemple fil rouge

Un pays A adopte un plafond de prix : c'est une contrainte économique, un fait daté. Un pays B annonce
des représailles : la relation se polarise. On se demande : un franchissement de seuil géopolitique
aura-t-il lieu d'ici trois mois ?

Le dépôt écrit cette situation en une phrase :

```
[2026-09 | 3 mois] POLARITÉ@7[F] + CONTRAINTE@6[F]
```

Lisez-la à voix haute : « en septembre 2026, sur une fenêtre de trois mois, une polarité géopolitique
forte et une contrainte économique forte sont ancrées. » C'est tout. L'état n'est pas un score, ni un
vecteur de 300 dimensions : c'est une phrase datée, lisible par un humain, contestable par un autre.

Notez la strate : la sanction est un fait de strate 7 (décision entre États) ; ses effets sur les prix
sont des faits de strate 6. Ce sont deux faits, pas un. Et `CONTRAINTE@6` influencera `SEUIL@7` par une
arête de matrice **abaissée d'un cran**, sans propagation documentée — un fait que le moteur signale
depuis 0.7.3 et qui relève de « À vérifier ».

### 2.2 · Les sept gestes

**Phase A — Lire**

1. **Rattacher les faits aux strates.** Pas selon le thème, mais selon le mécanisme. Un même fait ne
   peut ancrer qu'un mot par strate.

2. **Choisir 2 à 4 cartes candidates, par strate, dont une contre-candidate.** Depuis 0.7.4, chaque
   candidate non retenue est déclarée avec le motif de son rejet (`rejets`), y compris une rivale jamais
   ancrée. C'est une correction de fond : auparavant, toute candidate devait être ancrée, ce qui
   interdisait de déclarer une rivale écartée et rendait la contre-candidate tautologique.

3. **Ancrer.** Un fait ancre une carte s'il remplit un marqueur de son équivalent local. La force F n'est
   pas « je suis sûr » : elle exige un **test de preuve suffisant** (« pistolet fumant » ou « doublement
   décisif » ; un fait qui remplit seulement le marqueur est un cerceau, il donne f), une **ligne A6**
   qui passe toutes les cartes voisines avec une justification pour chacune, une **garantie** en trois
   parties (mécanisme, attendu, ce qui contredirait), une **option** (le fait doit changer l'espace
   d'action de quelqu'un), une **corroboration** déclarée, et le **passage** lu qui soutient le fait tel
   qu'il est écrit. Une annonce ne prouve pas une réalisation ; « pourra être activé » ne soutient pas
   « a été activé ».

4. **Chercher la contradiction** (anti-résonance A7). On ne cherche pas « ce qui confirme », on cherche
   la contre-observation la plus forte **dans la situation**, par trois familles de requêtes :
   observation, discrimination, contradiction. Puis on classe sa portée : marginale (rien ne bouge),
   substantielle (F → f), dominante (rejet). Le rejet est un résultat normal, pas un échec. Depuis
   0.7.4, la recherche a un **plancher** : trois familles par carte de l'état, une discrimination par
   paire de candidates d'une même strate, requêtes consignées. En dessous, le dossier est incomplet et la
   lecture Spéculative. Le plancher porte sur les familles couvertes, pas sur un compte — une requête
   répétée compte une fois, et une requête formée sur le nom de sa carte est signalée.

**Phase B — Écrire**

5. **Écrire l'état daté.** Date, fenêtre, mots, liaisons, positions. Une carte apparaît au plus une fois
   par strate ; un état sans mot s'écrit ∅. Si aucune carte n'atteint « faible », l'état est nul : le
   dépôt le déclare et ne prévoit rien. C'est une issue normale, pas une humiliation.

**Phase C — Parier**

6. **Poser la question, puis sceller.** Deux questions sont obligatoires : (a) l'événement est-il fixé par
   un calendrier, a-t-il une durée de vie propre, ou ni l'un ni l'autre ? (b) la source de résolution
   mesure-t-elle bien le marqueur local, ou un phénomène voisin ? Puis on écrit sa propre probabilité, en
   chiffre, et on la scelle **avant** de lancer le moteur.

7. **Dossier scellé, puis calcul, puis journal.** Depuis 0.7.3, le calcul proprement dit est précédé
   d'une pièce qui n'existait pas : le **dossier de lecture**, validé par les mêmes fonctions qu'une
   fiche, qui rend un sceau. Le moteur refuse un état différent, un événement non déclaré, une sémantique
   ou une temporalité divergentes, des pièces postérieures à la date d'information. Puis il produit `p`,
   l'intervalle, les deux bandes, le comparateur sans cartes, le placebo, et les empreintes. À l'échéance,
   on score au Brier — sans jamais réécrire l'ancien pari. Une mise à jour est un nouvel identifiant.

> « Un pari non scoré n'est pas un risque, c'est une affirmation. »
> — Constitution, P6 · Falsifiabilité

### 2.3 · Le lexique minimum

| Terme | Ce que ça veut dire |
|---|---|
| **Strate** | Un domaine ou un niveau d'organisation. On y rattache les faits par leur mécanisme, pas par leur thème. |
| **Carte** | Une des 16 structures transversales. C'est une « lettre » de l'alphabet. |
| **Équivalent** | La traduction locale d'une carte dans une strate, avec ses marqueurs observables. Une case peut être vide : c'est une information. |
| **Ancrage** | Le fait précis qui remplit un marqueur. La force F/f dit la qualité de cet ancrage, jamais l'intensité physique du phénomène. |
| **Homologue** | Un cas passé qui s'écrit avec les mêmes cartes (H1), ou avec un recouvrement suffisant (H1.5, Jaccard pondéré ≥ 0,7). |
| **ρ** | Le niveau de risque d'une prévision (ρ0 à ρ4). Il dit d'où vient le chiffre, pas sa fiabilité. |
| **Brier** | La moyenne des carrés des écarts entre probabilité annoncée et issue (0 = parfait, 0,25 = hasard sur une binaire à 50 %). |
| **Barreau A** | Le premier barreau de l'échelle de Pearl : association. Le moteur ne répond ni à « que produirait telle action ? » ni à « que se serait-il passé autrement ? ». |
| **Dossier de lecture** | Depuis 0.7.3 : l'ensemble contrôlé des pièces d'une lecture (état, candidates, rejets, A6, A7, test, garantie, option, corroboration, passage, questions, requêtes, événements), scellé avant le calcul. |
| **Bande de modèle** | L'étendue de `p` quand les hypothèses non calibrées varient (λ, inerties, fréquence par défaut). |
| **Bande de classe** | L'étendue de `p` quand le **choix des cas** varie (Jaccard, lissages, demi-vie). Mesure l'incertitude sur la classe de référence, que la bande de modèle ignorait. |
| **Fragilité de niveau** | L'écart entre les `p` calculés sur chaque niveau d'homologie non vide. Il dit ce que le seuil `c_min_rho1` décide à lui seul. |
| **Placebo d'homologie** | `p` recalculé sur autant de cas tirés au hasard, dans la même strate et la même fenêtre. `p − p_placebo` = apport du **choix** des cas. |

### 2.4 · Ce que l'outil ne fait pas

Le dépôt est très explicite, et c'est à son honneur : il n'est pas un oracle (une prévision ρ4 symbolique
est autorisée, signalée, jamais dominante), pas un conseiller (il ne prescrit pas d'action), pas un
diagnostic (même dans la strate Psyché), pas une mémoire (il produit les lignes à conserver, il ne les
conserve pas), pas un modèle causal. Toute sortie se lit : « si le motif observé se répète, alors… ».

Depuis 0.7.3, il ne prétend plus non plus contrôler ce qu'il ne contrôle pas : sans `--dossier`, la
sortie écrit noir sur blanc que A1, A3, A6, A7, les questions et la définition de l'événement n'ont pas
été vérifiés. C'est un aveu d'ignorance intégré au produit, et c'est plus rare qu'il n'y paraît.

---

## 03 · L'axiome du dépôt

> Ce que l'alphabet suppose pour que sa prévision ait un sens — et ce qu'il ne suppose pas.

> « Deux situations qui s'écrivent avec les mêmes lettres ont le même avenir distributionnel. »
> — Formulation vulgarisée de l'axiome d'homologie structurelle

**Version précise** : si deux situations partagent la même configuration de structures — mêmes cartes,
mêmes forces, mêmes qualificatifs —, alors elles partagent la même distribution de transitions ; on peut
donc emprunter l'avenir des cas passés homologues.

Ce n'est pas l'axiome de CAMEO. CAMEO dit : « le politique est une chaîne d'actes typés ; la séquence des
types se répète ». L'alphabet dit quelque chose de plus fort : « la forme de la situation,
indépendamment de son domaine, détermine son avenir ». Le premier est une hypothèse de stationnarité sur
un vocabulaire d'actes ; le second est une hypothèse d'invariance structurelle. C'est plus ambitieux, et
c'est plus fragile.

### 3.1 · Quatre sous-axiomes, un méta-axiome

| Sous-axiome | Énoncé | Règle |
|---|---|---|
| **Décomposition** | Toute situation peut se décomposer en un petit nombre de structures transversales, éventuellement enchevêtrées. | P2, P3 |
| **Traduction** | Chaque carte se traduit dans chaque strate par un équivalent local, avec ses marqueurs. Une case vide est une information. | P2, A1, A3 |
| **Homologie** | La ressemblance entre situations est mesurable : mêmes cartes (H1), Jaccard pondéré ≥ 0,7 (H1.5), mêmes sources (H2), traduction entre strates (H3). | T3 |
| **Transition** | La matrice de transitions est assez stable pour être extrapolée ; les cas homologues corrigent l'a priori bayésien. | T2, T3 |
| **Méta-axiome** | L'universalité est une hypothèse, pas un point de départ ; la couverture n'est pas présumée. | P1, P8 |

Le méta-axiome est la partie la plus intéressante. La plupart des ontologies en sciences sociales
postulent leur universalité ; celle-ci la traite comme une hypothèse à tester strate par strate. C'est
intellectuellement plus honnête — mais cela a un coût : tant que le test n'est pas fait, l'axiome n'est
ni vrai ni faux, il est en attente.

### 3.2 · D'où vient cet axiome

Le dépôt n'invente pas l'idée de prévoir par analogie. Il l'inscrit dans une famille ancienne et
respectable, et il la formalise.

- **La méthode de Mill** (accord et différence) : comparer des cas pour isoler ce qui compte.
- **L'analyse historique comparée** (Skocpol, Tilly, Mahoney) : les trajectoires se comprennent par
  comparaison de configurations, pas par régression sur des moyennes.
- **Le raisonnement à base de cas** (Schank, Kolodner) : résoudre un problème neuf en retrouvant un
  problème passé qui lui ressemble, puis en adaptant sa solution.
- **Les analogies structurées** (Green & Armstrong, 2007) : une analogie choisie et documentée par des
  experts améliore la prévision par rapport au jugement non assisté — mais ne bat pas nécessairement un
  modèle statistique.
- **La prévision par classe de référence** (Kahneman & Tversky, 1979 ; Flyvbjerg, 2006) : avant de
  regarder le cas, regardez la distribution des cas comparables. C'est exactement ce que fait le moteur
  avec les homologues.
- **L'analyse qualitative comparée** (Ragin) : penser en configurations de conditions plutôt qu'en
  variables isolées. L'alphabet est, de ce point de vue, un QCA avec une matrice de transitions et un
  protocole de preuve.

Autrement dit : l'Alphabet situationnel est une **machine à analogies structurées**. Ce n'est pas un
défaut. C'est une famille méthodologique identifiable, avec sa littérature, ses succès et son problème
central.

### 3.3 · Le problème central : la classe de référence

Pour CAMEO, la classe de référence est donnée : tous les pays-mois, sur plusieurs décennies. Pour
l'alphabet, elle est **construite** : les cas qui ont un Jaccard pondéré ≥ 0,7 sur 16 cartes. Ce choix —
le seuil, les poids (F = 1, f = 0,5), les dimensions retenues — détermine largement la prévision. Le
dépôt le reconnaît : la similarité « ne code pas l'identité des objets, les positions ou les liaisons ».

Trois conséquences, déjà identifiables avant toute donnée :

1. **Le même cas peut être apparié à des passés différents selon le seuil.** Baisser le seuil augmente
   l'effectif et diminue la comparabilité ; le hausser fait l'inverse. Le dépôt choisit le niveau le plus
   strict qui atteint 3 cas — compromis raisonnable, mais compromis.
2. **Le Jaccard sur 16 cartes est grossier.** Deux situations très différentes peuvent partager 12
   cartes ; deux situations très proches peuvent différer sur une seule carte décisive. La similarité ne
   voit pas la saillance.
3. **Les dimensions omises peuvent être exactement celles qui comptent** : qui est l'acteur, quelle est
   la position de chacun, quel lien unit les cartes.

**Ce que les versions 0.7.3 et 0.7.4 changent ici — et c'est le cœur de cette note.** Le problème de la
classe de référence cesse d'être une objection de principe : il devient mesuré à chaque calcul, par trois
instruments distincts.

| Instrument | Ce qu'il fait varier | Ce qu'il révèle |
|---|---|---|
| Bande de classe (0.7.3) | Jaccard ± 0,1 ; k et k₀ × ½ et × 2 ; demi-vie × ½ et × 2 | la sensibilité de `p` au **paramétrage** du choix des cas |
| Fragilité de niveau (0.7.3) | le niveau d'homologie retenu (H1, H1.5, H2) | l'écart que le seuil `c_min_rho1` décide seul |
| Placebo (0.7.4) | les cas eux-mêmes, tirés au hasard à effectif égal | l'apport du **contenu** du choix, au-delà de l'effectif |

Les deux premiers mesurent la robustesse du réglage. Le troisième mesure l'hypothèse elle-même. C'est
la distinction décisive : une bande étroite pouvait auparavant se lire « ma prévision est robuste »,
alors qu'elle ne disait rien sur le fait que les **bons** cas aient été retenus.

**Ce que la démonstration montre, et ce qu'elle ne montre pas.** Sur la base fictive du dépôt, pour
l'événement phare : `p = 22,0 %`, sans cartes `12,1 %`, placebo `20,2 %`. Les cartes déplacent donc la
probabilité de 10,0 points, mais le choix des cas n'en explique que 1,8 — environ 18 %. Sur cinq
événements de la même démonstration, l'apport moyen des cartes est de **+0,9 point** et celui de
l'homologie de **+0,7**, soit environ 79 % de l'effet. Le rapport s'inverse parce que l'effet des cartes
est très hétérogène : fortement positif sur un événement, légèrement négatif sur les quatre autres. La
moyenne écrase le premier et laisse l'homologie seule, faiblement, en positif.

Trois choses à ne pas conclure :

- **Ce n'est pas un résultat sur l'axiome.** La base est inventée. Un chiffre sur une base inventée mesure
  la mécanique du moteur, pas le monde.
- **Ce n'est pas non plus un non-résultat.** L'instrument sépare désormais deux causes qui étaient
  confondues : le multiplicateur a priori et la sélection des cas. Avant 0.7.4, « les cartes apportent
  10 points » était la seule phrase disponible, et elle était ambiguë.
- **Ce qui est inquiétant n'est pas la taille de l'apport, c'est sa distribution.** L'effet des cartes est
  très hétérogène selon l'événement : fortement positif sur l'événement phare, légèrement négatif sur
  quatre autres. Si ce profil se reproduit sur des cas réels, il signifiera que le dispositif fonctionne
  pour certains types de questions et dégrade pour d'autres — ce qui est une information utile, et non un
  échec.

**Ce qu'il faudrait tester.** Trois choses, dans cet ordre : (1) la **stabilité de la classe** — le même
cas, à ± 0,1 de seuil, donne-t-il le même avenir ? (2) la **pertinence** — les homologues retenus
ressemblent-ils au cas sur des dimensions que l'on n'a pas utilisées pour les choisir ? (3) le
**placebo** — des cas choisis au hasard dans la même strate donnent-ils une meilleure ou une pire
prévision ? Le point (1) est désormais calculé à chaque prévision, le point (3) aussi ; le point (2)
reste entièrement à faire, et c'est le seul qui exige des cas réels.

### 3.4 · Ce que l'axiome ne dit pas

| Il ne dit pas… | Parce que |
|---|---|
| « la structure cause la transition » | Le moteur est associationnel (barreau A). Il extrapole des motifs observés ; il ne répond pas à « que produirait telle action ? ». |
| « la même structure a les mêmes dynamiques partout » | L'emprunt entre strates (T4) est fermé tant que les équivalents des deux strates ne sont pas Documentés ou Attestés. Le transfert n'est pas acquis. |
| « l'alphabet couvre tout » | P8 : la couverture n'est pas présumée. Un motif non décrit va au journal des lacunes ; c'est la seule entrée vers une nouvelle carte (A2). |
| « la probabilité est calibrée » | P5 et les niveaux ρ : le chiffre dit d'où il vient, pas quelle confiance lui accorder. Aucune calibration prospective n'est acquise. |
| « l'apport des cartes mesure l'analogie » | Depuis 0.7.4, non : l'apport des cartes mesure l'effet conjoint du prior et de l'homologie ; seul l'écart au placebo mesure la seconde. |

---

## 04 · Dix expériences abouties

> Du codage des actes au modèle de langue. Pour chacune : le dispositif, le résultat, l'axiome en une
> phrase, et ce qu'elle prouve — ou pas.

*« Aboutie » veut dire : publiée, évaluée, répliquée ou contestée publiquement. Les chiffres sont ceux
des articles ; les axiomes sont des reformulations vulgarisés, pas des citations. Une expérience peut
être aboutie et son axiome faux : c'est même le cas le plus instructif.*

| Expérience | L'axiome en une phrase |
|---|---|
| CAMEO / GDELT / ICEWS | Le politique est une chaîne d'actes typés ; la séquence des types contient le prochain. |
| Chadefaux, 2014 | La guerre se dit avant de se faire. |
| Mueller & Rauh, 2018 | Ce n'est pas le mot, c'est le déplacement du mélange thématique. |
| Baker, Bloom & Davis, 2016 | L'incertitude privée se lit dans les mots publics. |
| Tetlock 2007 · Lazy Prices 2020 | Le changement de formulation est un aveu. |
| Bollen et al., 2011 | L'humeur collective précède le marché. |
| Google Flu Trends, 2009 | Le symptôme précède la maladie. |
| Halawi 2024 · Schoenegger 2024 | Le futur est latent dans le corpus. |
| D'Orazio & Yonamine, 2015 | Les séquences qui précèdent un conflit ont une forme reconnaissable. |
| Chadefaux & Schincariol, 2025 | Le conflit est autorégressif : le passé récent bat la structure profonde. |

### 4.0 · CAMEO, GDELT, ICEWS — le point de départ

**2002–2013 · Gerner, Schrodt et al. · Leetaru & Schrodt.**
CAMEO est une ontologie d'événements politiques : une vingtaine de catégories racines, quelques
centaines de sous-codes, un codage des acteurs. Chaque dépêche est réduite à une fiche : qui fait quoi à
qui, quand, où. GDELT applique ce codage en continu à une masse énorme de presse mondiale ; ICEWS,
programme de la DARPA, l'utilise pour produire des prévisions de crise. Brandt, Freeman et Schrodt (2011)
combinent CAMEO avec des modèles à changements de régime et des VAR bayésiens pour prévoir le conflit
israélo-palestinien.

> « Le politique est une chaîne d'actes typés : si l'on sait qui a fait quoi, la séquence des types
> d'actes contient l'information nécessaire pour prévoir le prochain. »

**Ce que ça a donné.** Un flux d'événements massif, utilisable en temps réel, et des estimations
immédiates honorables sur les événements fréquents et proches. Mais les évaluations publiées
convergent : les événements rares (coups d'État, rébellions, ruptures) restent mal prédits, et les
données d'événements sont sensibles aux biais de couverture médiatique (Weidmann, 2015).

**Ce que ça prouve.** Un codebook fixe, appliqué à grande échelle, produit une mesure utile de
l'interaction politique. La discipline du vocabulaire fermé est une force, pas une limite.

**Ce que ça ne prouve pas.** Que l'acte soit la bonne unité pour les ruptures. CAMEO ne voit ni seuil, ni
dépendance au chemin, ni contrefactuel. Et la presse n'est pas un miroir neutre.

**Ce que le dépôt peut emprunter.** Le flux GDELT/ICEWS comme flux de faits pour la strate 7 — pas comme
modèle. Et la discipline d'un codebook fermé, déjà présente avec les 16 cartes.

### 4.1 · Compter les mots — Chadefaux, 2014

**Journal of Peace Research 51(1).** Au lieu de coder des actes, on mesure la fréquence et la tonalité
des mots liés au conflit dans la presse, pour un pays donné. L'hypothèse : quand le vocabulaire se
charge, la guerre approche. C'est l'ancêtre direct de l'intuition « le langage précède l'événement » —
sans structures, avec un simple signal lexical.

> « La guerre se dit avant de se faire : la fréquence des mots consacrés à un pays dérive avant
> l'attaque. Le texte est un précurseur, pas seulement un reflet. »

**Ce que ça a donné.** L'article revendique qu'un signal lexical simple prédit l'apparition de la guerre
au moins aussi bien que les modèles structurels classiques sur son échantillon ; il a été primé et
beaucoup cité. La portée prospective reste discutée, comme toujours avec les corpus uniques.

**Ce que ça prouve.** Le texte contient de l'information en avance sur les covariables structurelles
lentes ; une mesure simple et transparente peut battre un modèle coûteux.

**Ce que ça ne prouve pas.** Un mécanisme. La couverture médiatique est endogène : on parle plus d'un
pays quand il va mal, et l'on peut confondre le symptôme avec la cause.

### 4.2 · Lire les thèmes — Mueller & Rauh, 2018

**APSR 112(2).** Des modèles thématiques réduisent des quantités massives de presse à des thèmes
interprétables, qui entrent ensuite dans des régressions de panel. Le point clé : ce n'est pas le niveau
des thèmes qui compte, c'est leur **variation à l'intérieur d'un même pays**. Cela évite de ne prédire
du conflit que là où il y en a déjà eu.

> « Ce n'est pas le mot qui compte, c'est le déplacement du mélange thématique : quand les sujets du
> journal changent, le risque change. »

**Ce que ça a donné.** Les thèmes prédisent l'apparition du conflit, et surtout dans les pays jusque-là
pacifiques — précisément là où les modèles structurels sont aveugles. Les auteurs l'expliquent par la
profondeur et la largeur des topics : ils voient aussi les facteurs stabilisateurs.

**Ce que ça prouve.** Le texte apporte de l'information absente des covariables structurelles, et la
variation intra-pays est plus informative que la comparaison entre pays.

**Ce que ça ne prouve pas.** Que les thèmes soient stables, interprétables causalement, ou que le
résultat tienne hors échantillon. C'est un modèle de panel, pas une théorie.

**Leçon pour l'alphabet.** La grammaire est déjà une grammaire de variation : des états datés qui se
succèdent. C'est un avantage sur les modèles qui comparent des pays à un instant. Il faut l'exploiter :
prédire le **changement d'état**, pas le niveau.

### 4.3 · Mesurer l'incertitude — Baker, Bloom & Davis, 2016

**QJE.** Compter, dans les journaux, les articles qui contiennent à la fois un terme économique, un
terme de politique publique et un terme d'incertitude. Le résultat est un indice mensuel, l'Economic
Policy Uncertainty. Mais une réplication de 2025 (Canadian Journal of Economics) trouve que l'effet
négatif sur l'activité disparaît sur la sous-période 2008–2019, avant de revenir avec le COVID. Le
thermomètre reste utile ; la relation qu'il mesurait n'est pas stable.

**Ce que ça prouve.** Un indice textuel transparent, reproductible et peu coûteux peut mesurer une
variable latente et corréler avec le comportement.

**Ce que ça ne prouve pas.** Que l'indice mesure une seule chose, ni que la corrélation tienne sur toutes
les périodes. Un bon thermomètre n'est pas un médicament.

### 4.4 · Le ton et le changement — Tetlock 2007, Hassan et al. 2019, Lazy Prices 2020

Trois variantes de la même idée. Tetlock mesure le pessimisme d'une chronique boursière. Hassan et al.
mesurent la part d'une conférence de résultats consacrée au risque politique. Lazy Prices compare les
dépôts 10-K d'une année sur l'autre : ce n'est pas le texte qui compte, c'est le **changement** de texte.

> « Le ton et le changement de formulation sont des choix coûteux : ils trahissent une information que
> les acteurs n'ont pas encore intégrée. »

**Ce que ça a donné.** Le pessimisme prédit le volume et les prix ; le risque politique est associé à une
réduction de l'embauche et de l'investissement, et à plus de lobbying ; Lazy Prices obtient jusqu'à
188 points de base par mois d'alpha, et le signal prédit aussi les résultats, les annonces et les
faillites.

**Ce que ça prouve.** Le langage est un signal coûteux, pas un simple reflet ; le changement est plus
informatif que le niveau ; le résultat tient hors échantillon en finance.

**Ce que ça ne prouve pas.** Un mécanisme causal, ni la transposabilité hors du domaine. Les
dictionnaires sont spécifiques ; le signal peut être une diffusion lente, pas une cause.

**Leçon pour l'alphabet.** La carte TRANSFORMATION est exactement cela : une entité qui change de forme
en conservant un invariant. Le résultat de Lazy Prices suggère de coder le changement de la situation,
pas seulement son état.

### 4.5 · Deux échecs qui enseignent plus que bien des succès

**4.5a · L'humeur sur Twitter — Bollen et al., 2011.** Un modèle de l'humeur collective extraite de
tweets prédit la direction du Dow Jones avec 87,6 % d'exactitude, sur un échantillon de février à
décembre 2008. **La réplication.** Lachanski & Pav (2017) ne retrouvent pas le résultat : l'effet existe
dans le sous-échantillon d'origine, pas dans l'échantillon étendu, et aucune prédiction hors échantillon
ne fonctionne. Le fonds Derwent, lancé pour exploiter la stratégie, a fermé en 2012.
*Leçon* : un résultat spectaculaire sur un seul échantillon est une hypothèse, pas une découverte. Le
dépôt a déjà l'antidote : le journal et le test à l'aveugle.

**4.5b · Google Flu Trends — Ginsberg 2009, Lazer 2014.** Les requêtes liées à la grippe semblent un
thermomètre en temps réel, avec une à deux semaines d'avance sur les CDC. **La dérive.** De 2011 à 2013,
GFT surestime la grippe 100 semaines sur 108 ; au pic de 2013, il annonce deux fois les cas réels. En
cause : 50 millions de termes ajustés sur 1 152 points, un moteur de recherche qui change, et une boucle
de rétroaction. *Leçon* : un modèle entraîné sur un monde qui bouge se périme. Une ontologie « lente »
est moins exposée à cette dérive — mais elle peut se tromper de façon stable.

### 4.6 · Confier le texte au modèle — Halawi 2024, Schoenegger 2024

Halawi et al. construisent un système qui cherche des articles, les résume, raisonne et agrège des
prévisions, testé sur des questions publiées après la date de coupure des modèles. Schoenegger et al.
font concourir un ensemble de 12 LLM contre 925 prévisionnistes humains sur 31 questions binaires.

> « Le futur est déjà latent dans le corpus : un modèle qui a lu le monde, et à qui l'on donne les
> bonnes informations du jour, produit une distribution proche de celle d'une foule de prévisionnistes. »

**Ce que ça a donné.** Halawi : Brier 0,179 contre 0,149 pour la foule (0,250 = hasard) ; en zero-shot,
le meilleur modèle est à 0,208 ; dans l'un des modes sélectifs, 0,238 contre 0,240. Schoenegger :
l'ensemble de LLM est statistiquement indiscernable de la foule humaine ; exposer les modèles à la
médiane humaine améliore leurs prédictions de 17 à 28 % ; et la moyenne humain + machine reste la
meilleure.

**Ce que ça prouve.** Avec récupération d'information et agrégation, les LLM approchent la foule
humaine. Le gain vient de la récupération et de l'agrégation, pas d'une « compréhension » brute.

**Ce que ça ne prouve pas.** Que le modèle n'ait pas déjà vu la réponse — la contamination est un
confond majeur — ni que la foule humaine ne reste pas la référence la plus forte.

**Leçon pour l'alphabet.** Ne pas utiliser le LLM comme oracle : comme second codeur et comme
comparateur. Depuis 0.7.3, le dossier de lecture scellé est précisément la pièce qu'un second codeur peut
relire sans avoir assisté au calcul.

### 4.7 · Les deux résultats les plus proches du dépôt

**4.7a · La similarité de séquences — D'Orazio & Yonamine, 2015 (PLoS ONE).** Ils comparent les séquences
d'événements qui précèdent un conflit intra-étatique à celles qui précèdent la paix, avec trois mesures de
similarité : euclidienne, Levenshtein, information mutuelle. C'est, à notre connaissance, le test le plus
proche de H1.5.

*Résultat* : le modèle classe bien les séquences qui précèdent la paix, mais ne distingue pas les cas où
une seule séquence escalade de ceux où les deux escaladent. Autrement dit : la similarité est un bon
détecteur de normalité, un mauvais détecteur de rupture.

*Leçon* : c'est le mur que H1.5 va rencontrer. Il faut le savoir avant de lancer le test.

**4.7b · L'autorégression bat la structure — Chadefaux & Schincariol, 2025 (EPJ Data Science).** Ils
comparent des modèles autorégressifs simples à des modèles complexes à covariables structurelles, sur
plusieurs pays et spécifications.

*Résultat* : les modèles autorégressifs égalent ou battent les alternatives complexes ; les covariables
structurelles ajoutent peu ou dégradent la performance. Le conflit est un processus endogène, fait de
rétroaction, de sursauts et d'adaptation à court terme.

*Leçon* : le comparateur `p_sans_cartes` est le bon juge. Si les cartes ne battent pas l'inertie, elles ne
servent à rien pour la prévision — même si elles servent à la lecture.

**Le résultat qui doit inquiéter le plus.** Ce ne sont pas les échecs de GFT ou de Bollen : ce sont ces
deux articles de 2015 et 2025. Ils disent, avec des données, que la similarité de séquences distingue la
paix mais pas l'escalade, et que l'inertie bat souvent la structure. L'axiome n'est pas réfuté par eux —
mais il est sérieusement mis en doute, et il devra leur répondre explicitement.

---

## 05 · Comparaison

> Même chaîne, deux ontologies. Ce qui change n'est pas le pipeline : c'est ce qu'on met dans la première
> case.

Toutes ces expériences suivent la même chaîne : texte → code → état → transition → pari. Ce qui les
distingue, c'est le **code** — l'unité que l'on garde — et la **classe de référence** — les cas à qui
l'on compare. Le dépôt est original sur les deux, et c'est précisément là qu'il est le plus exposé.

| Dimension | CAMEO / GDELT / ICEWS | L'Alphabet situationnel |
|---|---|---|
| Ce qui est codé | un acte : verbe, acteur, cible | une structure : 16 cartes, 13 strates |
| Unité d'observation | événement daté, jour ou semaine | état daté, fenêtre (souvent 3 mois) |
| Qui code | algorithmes (PETRARCH, POLECAT, BBN) | humain ou modèle, avec les contrôles A5–A7 et un dossier scellé |
| Corpus | millions de dépêches | quelques faits lus et cités |
| Moteur | comptages, Markov, VAR bayésien, logit | bayésien de cas + matrice de 66 transitions |
| Classe de référence | panel pays-mois : **donnée** | cas homologues : **construite** (Jaccard ≥ 0,7) |
| Validation | backtests sur des décennies | 0 cas actif ; V4 non atteint |
| Type d'affirmation | prédiction, souvent implicite | association déclarée (barreau A) |
| Force | échelle, reproductibilité, estimation immédiate | profondeur, traçabilité, falsifiabilité |
| Faiblesse | validité de construit, biais médias | fiabilité du codeur, coût, calibration |

### 5.1 · Ce que chaque famille peut apporter

| Famille | Emprunt concret | Pourquoi c'est utile |
|---|---|---|
| CAMEO / GDELT / ICEWS | le flux d'événements comme faits pour la strate 7 ; un codebook fermé | réduit le coût de codage, augmente la reproductibilité, donne des dates et des sources vérifiables |
| Chadefaux, EPU | un comparateur lexical simple ; comparer un pays à son propre passé | un comparateur transparent ; la logique intra-pays est déjà dans la grammaire |
| Tetlock, Lazy Prices | coder le changement d'état (TRANSFORMATION), pas seulement le niveau | le changement est plus informatif que le niveau ; la carte TRANSFORMATION est faite pour cela |
| LLM | second codeur à l'aveugle, comparateur de prévision, assistant de récupération | débloque A4 et κ sans recruter ; fournit un point de comparaison crédible |
| D'Orazio 2015, Chadefaux 2025 | les deux tests que la méthode doit passer : similarité de séquences, incrément sur l'inertie | ce sont les deux objections les plus solides à l'axiome |

### 5.2 · Face-à-face avec l'axiome

**CAMEO : même chaîne, autre code.** Le dépôt gagne la profondeur (un seuil, une dépendance au chemin),
il perd l'échelle et la reproductibilité automatique. Leur force est de coder des millions d'actes ; la
sienne est de coder ce qu'un acte ne dit pas.

**Chadefaux, Mueller & Rauh : même intuition, autre extraction.** Ils laissent l'algorithme choisir les
mots et les thèmes ; le dépôt laisse l'humain choisir les structures. Eux gagnent en couverture, lui
gagne en interprétabilité — et paie en fiabilité de codeur.

**Tetlock, Lazy Prices : même idée que le changement compte, autre objet.** Ils codent le changement de
formulation ; le dépôt code le changement de structure. Leur signal est involontaire et bon marché ; le
sien est intentionnel et coûteux.

**LLM : même pari sur le corpus, autre moteur.** Le LLM apprend la distribution des suites de mots ; le
dépôt postule la distribution des suites de structures. Eux peuvent tout lire sans expliciter leurs
raisons ; lui peut peu lire mais explicite chaque pas.

> « La différence n'est pas dans la chaîne : elle est dans l'ontologie et dans la classe de référence.
> C'est là que se joue la validation — et c'est là que le dépôt est le plus seul. »

### 5.3 · Ce que le placebo change dans cette comparaison

La comparaison ci-dessus laissait une ambiguïté, désormais levée par un dispositif dont, à notre
connaissance, aucun des dix travaux cités ne comporte d'équivalent.

CAMEO, les thèmes, les dictionnaires, les LLM : tous ont une classe de référence **donnée** par la
construction du corpus. Ils ne peuvent pas se demander « et si j'avais comparé à d'autres cas ? », parce
qu'il n'y a pas d'« autres cas » : tout le corpus est la référence. L'alphabet, lui, choisit ses cas. Ce
choix était son point faible — c'est aussi la seule position d'où l'on peut faire un placebo.

Le placebo n'est donc pas un ornement méthodologique de plus : c'est le test que seule une ontologie à
classe construite peut passer, et il transforme une faiblesse structurelle en instrument de mesure. La
littérature ne fournit pas de précédent direct ; la logique est celle des essais contrôlés, transposée à
la sélection des cas.

---

## 06 · Ce que ça dit du dépôt

> Trois forces que la littérature n'a pas, trois faiblesses qu'elle corrige, et un mur à regarder en face.

### 6.1 · Quatre forces que la littérature n'a pas

**Un protocole falsifiable.** Pré-enregistrement, jugement scellé avant le moteur, dossier de lecture
scellé avant le calcul, Brier, décomposition de Murphy, abstentions, difficulté des questions, deux
bandes de sensibilité, placebo. Une grande partie des travaux de prévision par NLP ne pré-enregistrent
rien et ne mesurent pas ce que le modèle ajoute au jugement humain. Ici, si — et depuis le 29 octobre
2026, une prévision qui n'a pas de dossier scellé ne compte pas dans le jalon de validation.

**Une théorie de la preuve.** A5–A7 ne sont pas un codeur : c'est une épistémologie du codage. Le test de
preuve (paille, cerceau, pistolet, double), la garantie, l'option, le passage, l'anti-résonance avec
plancher de familles. Peu de projets vont aussi loin dans la discipline du fait. Depuis 0.7.3, cette
théorie **s'applique là où elle comptait** : elle était vérifiée pour les fiches historiques, jamais pour
la lecture qui produit une probabilité. C'était le trou le plus coûteux du dépôt, parce qu'il portait sur
ce que le dépôt présentait comme sa force principale.

**Une hygiène des chiffres.** F/f n'est pas une intensité. « Non estimé » n'est pas converti en chiffre.
ρ dit d'où vient le chiffre, pas sa fiabilité. Le barreau A est déclaré. L'apport des cartes n'est plus
présenté comme un apport quand l'a priori n'est pas ancré. Et la sortie dit ce qu'elle n'a pas contrôlé.

**Une architecture qui sépare les causes d'un score.** C'est la force la plus discrète et la plus utile.
Quatre diagnostics distincts — inertie, modèle, classe, homologie — permettent de savoir *pourquoi* un
chiffre est ce qu'il est. Aucun des dix travaux cités ne fournit cette décomposition. C'est ce qui rendra
un éventuel résultat nul interprétable : « la structure n'ajoute rien » cessera d'être un échec indistinct
pour devenir un diagnostic localisé.

Ces quatre choses sont publiables en soi. Un article de méthode qui n'a pas encore de résultat peut être
plus utile que dix articles à +0,02 d'AUC. Et il a un avantage stratégique : il ne peut pas être réfuté
par un mauvais score.

### 6.2 · Trois faiblesses que la littérature corrige

| Fait | Conséquence | Remède |
|---|---|---|
| **0 cas actif** | Aucune performance hors échantillon. Le dépôt ne peut revendiquer aucune prédiction. | Coder 20 cas rétrospectifs sous les règles courantes, puis 5 à 10 prospectifs avant l'issue. |
| **1 codeur, κ absent** | La fiabilité du codage n'est pas mesurée. Un lecteur ne peut pas distinguer une lecture reproductible d'un art personnel. | Second codeur à l'aveugle (modèle + humain), κ par carte, désaccords conservés. |
| **182/208 « Proposé »** | L'ontologie est majoritairement non vérifiée. Les 13 « Documenté » sont tous en strate 7. | Finir la strate 7 (16/16), puis ouvrir une seconde strate. |

Ce ne sont pas des défauts de conception : ce sont des dettes. Mais une dette non payée finit par être un
défaut. Et le temps joue contre le dépôt : plus l'ontologie reste « Proposé », plus elle ressemble à une
taxonomie personnelle plutôt qu'à un instrument.

Une remarque sur la troisième ligne : le remède est souvent formulé comme « finir la strate 7 ». Or
`bilan` mesure aussi les cases **Vides closes** (trois recherches documentées) et les **Hors domaine**
motivés. Une strate « complète » n'est pas une strate où les 16 cartes sont Documentées : c'est une
strate où les 16 cases sont *traitées*, y compris par un constat d'absence. C'est plus honnête et plus
atteignable — et cela devrait être dit plus tôt au lecteur, parce que c'est la seule façon d'avoir une
strate pilote réellement close.

### 6.3 · Le mur

| Résultat empirique | Ce qu'il implique |
|---|---|
| La similarité de séquences distingue la paix, pas l'escalade (D'Orazio & Yonamine, 2015) | H1.5 peut être un bon classificateur de situations et un mauvais prédicteur de ruptures. Il faut tester séparément : la précision sur les états « normaux » ne dit rien sur les seuils. |
| L'autorégression égale ou bat les modèles structurels (Chadefaux & Schincariol, 2025) | Les cartes doivent battre `p_sans_cartes`, sinon elles n'ajoutent rien à la prévision. Le comparateur est le bon juge ; il faut le publier à chaque prévision. |
| Les mesures textuelles dérivent hors échantillon (GFT, Bollen) | Une ontologie « lente » est moins exposée à la dérive. Mais elle peut se tromper de façon stable : un biais de codebook ne se corrige pas avec plus de données. |
| **La sélection des homologues peut n'ajouter presque rien** (placebo, 0.7.4 — base fictive) | Si l'écart au placebo reste marginal sur des cas réels, le moteur mesure surtout son a priori et la fréquence de la strate, pas l'analogie structurelle. C'est testable, et désormais testé à chaque calcul. |

La quatrième ligne est nouvelle, et elle est de nature différente des trois autres : ce n'est pas un
résultat de la littérature, c'est le dépôt qui se mesure. Il faut la traiter avec la même prudence — la
base est fictive — mais aussi avec la même sérieux, parce qu'elle porte directement sur l'axiome et
qu'elle vient de l'intérieur.

**La conclusion honnête.** Le meilleur produit du dépôt n'est peut-être pas « prévoir des événements »,
mais « caractériser des situations, estimer leur persistance, et savoir ce que le chiffre doit à quoi ».
Ce n'est pas un échec : c'est un repositionnement. Un outil qui lit bien, qui date, qui documente, qui dit
« non estimé » quand il ne sait pas, et qui décompose ses propres chiffres a déjà une valeur — surtout
dans un domaine où tant d'outils sur-prédisent.

### 6.4 · Le bon cadrage

**Un article de méthode.** « Un protocole falsifiable de prévision par analogie structurelle, avec
décomposition de l'apport ». Le protocole *et* l'instrument de décomposition sont la contribution. Il
peut être publié avant les résultats, et il sera lu par les gens qui essaient de faire de la prévision
qualitative sérieuse.

**Un article de résultat nul.** « L'analogie structurelle n'ajoute rien au-delà du taux de base dans la
strate 7 » est un résultat utile, publiable, et parfaitement cohérent avec P8. Un résultat nul n'est pas
une défaite : c'est un résultat. Le dépôt est désormais outillé pour le produire proprement — ce qui est
exactement ce qu'on demande à un protocole.

**Un article de transfert.** La revendication trans-domaines (13 strates) doit être un test séparé, plus
tard, avec les mêmes cartes dans deux strates éloignées. Si les dynamiques ne se transportent pas,
l'hypothèse d'universalité est falsifiée — et c'est encore un résultat.

---

## 07 · Ce qui reste

> Six actions, classées par priorité. La première vaut plus que les cinq autres réunies.

### 7.1 · Ce que les versions 0.7.3 et 0.7.4 ont fermé

| Point | État |
|---|---|
| La lecture n'était pas contrôlée là où le chiffre naît | **fermé** — dossier de lecture validé avant le calcul, sceau, refus des divergences d'état, d'événement, de sémantique et de temporalité |
| La définition de l'événement n'était figée par rien | **fermé** — `evenements` déclarés au dossier, refus d'un événement non déclaré |
| La bande de sensibilité ignorait la classe de référence | **fermé** — huit variantes de classe, bande séparée, `origine_seuil` |
| Une bascule de niveau non signalée | **fermé** — `niveaux`, `fragilite_niveau`, seuil dédié à 10 points |
| L'apport des cartes interprété sans ancrage | **fermé** — mention conditionnelle, part de l'a priori dans la trace |
| Propagation inter-strates invisible | **fermé** — table des sources, alerte sur les arêtes abaissées par défaut |
| Sémantique et date d'information choisies par défaut | **fermé** — drapeaux explicites |
| Ordre d'abandon sous contrainte de contexte | **fermé** — section dédiée du `SKILL.md` |
| Le partage apprentissage/test n'était pas daté | **fermé** — registre daté, `usage_fige_le`, `codage.debut`, recoupement par `valider --registre` |
| A7 n'avait pas de plancher vérifiable | **fermé** — requêtes consignées, trois familles par carte, discrimination par paire de candidates |
| L'homologie n'était pas testable | **fermé** — placebo moyenné sur 200 tirages, graine dérivée de la question |
| F/f absent des multiplicateurs | **documenté, non corrigé** — décision réservée (voir 7.3) |

Trois écarts à la lettre des décisions valent d'être notés, parce qu'ils sont bien motivés et qu'ils
disent quelque chose de la maturité du projet : le partage se compare à `codage.debut` et non au premier
état, sinon tout cas historique serait refusé — donc le mode CODER entier ; le registre vit dans le
dossier de travail et non dans `assets/`, puisqu'il est remplacé à chaque installation ; le placebo est
moyenné sur 200 tirages plutôt qu'un tirage unique, trop bruité pour être lu. Chacun de ces écarts
remplace une règle littérale par une règle qui fait ce que la règle voulait faire.

### 7.2 · Ce qui reste

**P0 · Un second codeur, maintenant.** Prendre 20 cas, donner au second codeur uniquement les faits et
les dates de disponibilité, jamais le premier codage. Coder indépendamment. Calculer κ par carte. Si
κ < 0,6, réviser les marqueurs de la carte avant de continuer. Un modèle peut être ce second codeur — le
dépôt le prévoit (`role: modele`) — mais il faut au moins un humain. C'est ce qui débloque A4, la base, et
la crédibilité de tout le reste. **Le dossier scellé de 0.7.3 est exactement la pièce dont ce second
codeur a besoin** : il peut relire une lecture complète sans avoir assisté au calcul. C'est le meilleur
retour sur investissement des quatre décisions prises, et il était gratuit.

**P0 · Trois comparateurs dans chaque prévision.** L'inertie existe (`p_sans_cartes`). Le placebo existe
depuis 0.7.4. Il en manque un troisième : une prévision LLM zero-shot ou avec récupération. Publier les
trois écarts pour chaque question. Une prévision qui ne bat pas le meilleur comparateur est un
comparateur, pas un résultat.

**P1 · GDELT/ICEWS comme flux de faits, pas comme modèle.** Pour la strate 7, utiliser le flux
d'événements pour dater et sourcer les faits (A5), pas pour remplacer la lecture. On gagne en
reproductibilité et en coût sans abdiquer l'ontologie. C'est le pont le plus concret vers la littérature
CAMEO.

**P1 · Réduire la revendication.** Une strate (7), un type d'événement (`SEUIL@7 apparait`), 50 épisodes
pré-enregistrés. La revendication trans-domaines est un chapitre ultérieur, pas le premier article. Un
résultat étroit et solide vaut mieux qu'un résultat large et fragile.

**P2 · Publier le protocole et le résultat nul.** Le protocole est une contribution ; le résultat nul en
est une autre. Ouvrir la base, le journal et le registre de partage. Un dépôt public avec 50 épisodes,
des empreintes, des dossiers scellés et un Brier comparable à l'inertie et au placebo sera plus
convaincant qu'un article qui revendique 0,02 d'AUC sans preuve de prépublication.

**P2 · Tester le transfert entre strates, séparément.** Mêmes cartes, deux strates éloignées (1 ou 11
contre 7), même type d'événement. Si les dynamiques ne se transportent pas, P1 est falsifié — et c'est un
résultat. Ne pas mélanger ce test avec le test de performance : on ne saurait pas ce qui a échoué.

**P2 · Contrôle de calibration propre à SEUIL.** Sur les 50 épisodes, comparer la fréquence observée des
seuils à la fréquence prédite, séparément du Brier global. La matrice fait de SEUIL un point de passage
obligé de 14 liens entrants sur 66 ; un modèle peut sur-prédire les ruptures avec un Brier correct.

### 7.3 · La décision réservée : atténuer λ par la qualité de l'ancrage

C'est la seule des cinq décisions du 29 octobre qui n'est pas appliquée, et le dépôt a eu raison de la
réserver à une version séparée. Elle mérite une explication, parce qu'elle est la plus lourde.

**La question.** Aujourd'hui, le moteur demande « cette carte mène-t-elle à cet événement ? » et répond
par un nombre fixe de la matrice. Il ne demande jamais « quelle est la solidité de l'ancrage de cette
carte ? ». Deux témoins disent la même chose : l'un a des pièces, l'autre devine ; le moteur leur donne
le même poids. La proposition est `λ_eff = 1 + (λ − 1)·w`, avec w = 1 pour F et 0,5 pour f.

**L'argument pour.** C'est la seule façon de rendre A5–A7 numériquement payants. Aujourd'hui, un codeur
qui saute tout le travail de preuve obtient exactement le même nombre qu'un autre qui le fait. C'est une
incitation à sauter — et cela signifie que « nous avons une théorie de la preuve » est une affirmation
sur la documentation, non sur le calcul.

**L'argument contre, et il est sérieux.** Une fois la base peuplée, F/f entre **déjà** dans `p`, par
l'égalité H1 (force exacte) et par le Jaccard pondéré H1.5. Mesuré sur la démonstration : abaisser toutes
les forces d'un cran déplace `p` de +0,7 point, par la seule sélection des homologues. L'atténuation
ajouterait un second canal par-dessus un canal existant. Les deux sont partiellement colinéaires ; on ne
saurait pas lequel fait le travail, et le risque est de compter deux fois la même confiance.

**La décomposition qui rend la décision possible.** Il y a deux décisions, pas une : (a) le **principe** —
la qualité de la preuve doit-elle atténuer l'inférence ? C'est une décision de conception, qui peut être
prise sans donnée. (b) la **valeur** de w — c'est empirique, et il n'y a pas encore de données.

**Recommandation.** Oui au principe ; pas encore à la valeur. Implémenter l'atténuation comme variante
déclarée dans la bande de sensibilité, sans effet sur le `p` par défaut, mesurer, puis promouvoir au
défaut quand la base comptera une vingtaine de cas et que les deux canaux pourront être distingués. Cette
position respecte l'axiome : F/f n'est pas une intensité, mais une mesure peu fiable justifie une
inférence moins appuyée. C'est de l'atténuation pour erreur de mesure, pas une grandeur physique.

### 7.4 · Si une seule chose devait être gardée

**Le second codeur.** Pas parce que c'est la plus belle idée, mais parce que c'est la seule qui débloque
toutes les autres : sans κ, la base n'est pas une base ; sans base, le moteur n'a rien à réviser ; sans
révision, le journal ne mesure rien ; sans journal, ni le placebo ni le Brier ne veulent dire quoi que ce
soit. Vingt cas et un second codeur valent mieux que dix-sept cartes et un protocole parfait.

Le dépôt a maintenant tout ce qu'il faut pour que ce travail soit **opposable** : un dossier scellé pour
que le second codeur lise la même chose que le premier, un registre daté pour que le partage
apprentissage/test ne soit pas négociable, un placebo pour que l'apport de l'analogie ne soit pas
confondu avec celui du prior, un plancher de recherche pour que « j'ai cherché » soit constatable. Ce
qui manque n'est plus de la méthode. Ce sont des faits, un deuxième lecteur et une issue.

---

## 08 · Sources

### Le dépôt et ses vérifications

`Othman-Benbrahim/alphabet-situationnel`, version 0.7.4, licence MIT. Fichiers lus : `README.md`,
`SKILL.md`, `references/` (constitution, protocole, grammaire, graphe, dynamiques, validation,
feuille-de-route, glossaire, angles-morts, apports-théoriques, 13 fichiers d'équivalents),
`assets/parametres.json`, `assets/base-de-cas.exemple.jsonl`, `assets/dossier.exemple.json`,
`CHANGELOG.md`, `scripts/moteur.py`.

Commandes exécutées le 29/10/2026 :

```
python3 scripts/moteur.py audit      → conforme
python3 scripts/moteur.py autotest   → 115 tests
python3 scripts/moteur.py bilan      → 0 cas actif · 13/16 en strate 7 · aucun journal
python3 scripts/moteur.py calculer … --demo    → p 22,0 % [5,2–43,1] · sans cartes 12,1 %
                                                 placebo 20,2 % · apport homologie +1,8 pt
```

### Codage des événements

- Gerner, D., Schrodt, P., Yilmaz, Ö., Abu-Jabr, R. (2002). *Conflict and Mediation Event Observations
  (CAMEO).*
- Leetaru, K., Schrodt, P. (2013). *GDELT: Global Data on Events, Location and Tone.*
- Brandt, P., Freeman, J., Schrodt, P. (2011). *Real Time, Time Series Forecasting of Inter- and
  Intra-State Political Conflict.* Conflict Management and Peace Science 28(1).
- Weidmann, N. B. (2015). *A Closer Look at Reporting Bias in Conflict Event Data.* AJPS.

### Texte, ton et prévision

- Chadefaux, T. (2014). *Early Warning Signals for War in the News.* Journal of Peace Research 51(1).
- Mueller, H., Rauh, C. (2018). *Reading Between the Lines: Prediction of Political Violence Using
  Newspaper Text.* APSR 112(2).
- Baker, S., Bloom, N., Davis, S. (2016). *Measuring Economic Policy Uncertainty.* QJE ; réplication de
  2025 dans le Canadian Journal of Economics.
- Tetlock, P. (2007). *Giving Content to Investor Sentiment.* Journal of Finance 62(3).
- Hassan, T., Hollander, S., van Lent, L., Tahoun, A. (2019). *Firm-Level Political Risk: Measurement and
  Effects.* QJE.
- Cohen, L., Malloy, C., Nguyen, Q. (2020). *Lazy Prices.* Journal of Finance.

### Échecs et réplications

- Bollen, J., Mao, H., Zeng, X. (2011). *Twitter Mood Predicts the Stock Market.* J. Computational
  Science 2(1).
- Lachanski, M., Pav, S. (2017). *Shy of the Character Limit.* Econ Journal Watch.
- Ginsberg, J. et al. (2009). *Detecting Influenza Epidemics Using Search Engine Query Data.* Nature.
- Lazer, D., Kennedy, R., King, G., Vespignani, A. (2014). *The Parable of Google Flu.* Science.

### Modèles de langue et prévision

- Halawi, D., Zhang, F., Yueh-Han, C., Steinhardt, J. (2024). *Approaching Human-Level Forecasting with
  Language Models.*
- Schoenegger, P. et al. (2024). *Wisdom of the Silicon Crowd.* Science Advances.
- Karger, E. et al. (2022). *Forecasting Future World Events with Neural Networks.*

### Analogies, cas et limites

- Green, K., Armstrong, J. S. (2007). *Structured Analogies for Forecasting.* IJF 23(3).
- Kahneman, D., Tversky, A. (1979). *Prospect Theory.* Econometrica 47(2).
- Flyvbjerg, B. (2006). *From Nobel Prize to Project Management: Getting Risks Right.*
- Van Evera, S. (1997) ; Collier, D. (2011). Tests de process tracing (paille, cerceau, pistolet,
  double). PS 44(4).
- Hegre, H. et al. (2019). *ViEWS: A Political Violence Early-Warning System.* JPR 56(2).
- D'Orazio, V., Yonamine, J. (2015). *Kickoff to Conflict.* PLoS ONE.
- Chadefaux, T., Schincariol, T. (2025). *Endogenous Conflict and the Limits of Predictive Optimization.*
  EPJ Data Science.
- Murphy, A. H. (1973). *A New Vector Partition of the Probability Score.* J. Appl. Meteor. 12, 595-600.

*Note préparée le 29 octobre 2026, révisée pour la version 0.7.4. Les chiffres de la démonstration
proviennent d'une base entièrement fictive (`--demo`) : ils illustrent la mécanique, pas une performance.
Les axiomes sont des reformulations vulgarisées, pas des citations des auteurs. Les positions et les
nombres de la matrice sont lus directement dans `assets/parametres.json`.*

---

## Annexe A · Journal des vérifications

| Vérification | Commande | Résultat |
|---|---|---|
| Intégrité | `moteur.py audit` | conforme — 208 statuts, 49 fichiers au manifeste, 131 renvois §, matrice et inerties |
| Régressions | `moteur.py autotest` | 115 tests |
| Avancement | `moteur.py bilan` | 0 cas actif, 13/16 en strate 7, 0/13 cases Vides closes, aucun journal |
| Placebo, événement phare | `calculer … --demo` | `p` 22,0 % · sans cartes 12,1 % · placebo 20,2 % · homologie +1,8 pt |
| Placebo, cinq événements | appels directs au moteur, base `--demo`, date d'information 2026-09 | cartes **+0,9 pt** en moyenne · homologie **+0,7 pt** · part de l'homologie 79 % |
| Fragilité de niveau | appels directs, base synthétique 2 cas H1 / 3 cas H1.5 | 53 % contre 33 %, soit 20 points décidés par `c_min_rho1` |
| Sonde de force | `calculer … --demo` | F → f : +0,7 pt, par la seule sélection des homologues |
| Matrice | lecture de `parametres.json` | 66/240 liens · 3 F · 27 M · 36 f · SEUIL 14 entrants, poids 21,6 |

*Les tests de fichiers temporaires (`test_repetitions`, `test_renvoi_detection`, `test_scorer_csv`,
`test_dossier_calculer`, `test_compose_sans_semantique`, `test_partage_date`) échouent sous un bac à sable
qui refuse l'écriture et le `chmod` dans le dossier temporaire du système. Ils n'échouent pas sur un
environnement non confiné ; ce n'est pas un défaut du code.*

## Annexe B · Ce qui a changé depuis la note du 28 octobre

| Point de la note du 28 octobre | État au 29 octobre 2026 |
|---|---|
| « 103 autotests » | **115** |
| « manifeste 48 fichiers » | **49** (dossier d'exemple ajouté) |
| « 127 renvois § » | **131** |
| « 182/208 Proposé, 0 Attesté » | inchangé |
| « 66 liens, 3 F, 27 M, 36 f » | inchangé |
| « le moteur ne teste pas la lecture » | **corrigé** — dossier scellé, 0.7.3 |
| « la bande de sensibilité ne bouge qu'un cran de λ » | **corrigé** — bande de classe, 0.7.3 |
| « le niveau d'homologie peut basculer sans que rien ne le signale » | **corrigé** — `fragilite_niveau`, 0.7.3 |
| « λ vient de la matrice, pas de F/f » | **écrit** dans `SKILL.md` et `graphe.md` §2.3, 0.7.3 |
| « l'apport des cartes n'a pas de sens sans ancrage » | **corrigé**, 0.7.3 |
| « propagation inter-strates invisible » | **affichée**, 0.7.3 |
| « le partage apprentissage/test n'est pas daté » | **corrigé** — registre daté, 0.7.4 |
| « A7 n'a pas de budget défini » | **corrigé** — plancher de familles, 0.7.4 |
| « aucun test de la sélection des homologues » | **corrigé** — placebo, 0.7.4 |
| « la revendication trans-domaines n'est pas testée » | inchangé — P2 |
| « un seul codeur, κ absent » | **inchangé — la dette principale** |
| « 0 cas actif » | **inchangé — la dette principale** |
