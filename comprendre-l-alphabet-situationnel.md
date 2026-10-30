# Comprendre l'Alphabet situationnel

### Un mode d'emploi en deux moitiés — et le fil qui les noue

**Document de vulgarisation · version 0.7.7 · révision 1 · 30 octobre 2026**

Ce texte accompagne la note [`analyse-alphabet-situationnel.md`](analyse-alphabet-situationnel.md). Il
ne la remplace pas : il explique, avec des mots ordinaires, ce que la note démontre avec des chiffres.
Il ne suppose aucune connaissance en mathématiques, en statistique ni en sémiotique.

---

## Avant de commencer

L'Alphabet situationnel est un outil qui fait deux choses, et qu'on confond souvent parce qu'elles sont
dans le même logiciel :

1. **il lit une situation** et la résume en une phrase datée, avec des mots choisis dans un vocabulaire
   fixe de seize formes ;
2. **il calcule** ce qui est arrivé, dans le passé, à des situations écrites de la même façon.

La première moitié est **sémiotique** : elle traite des signes, c'est-à-dire des faits qui veulent dire
quelque chose. La seconde est **mathématique** : elle traite des nombres, c'est-à-dire des fréquences et
des probabilités. Le génie de l'outil — et sa fragilité — tient dans la couture entre les deux.

Ce document est donc coupé en trois. La **partie I** décrit la lecture. La **partie II** décrit le
calcul. La **partie III** montre comment la première commande la seconde, et comment la seconde juge la
première. C'est la partie la plus importante, et c'est celle que les présentations techniques sautent
le plus souvent.

> **Une phrase pour tout retenir.** Le lecteur choisit les lettres ; le calcul choisit les nombres ; le
> score dit si le lecteur avait raison de choisir ces lettres-là. Aucun des trois ne peut remplacer les
> autres.

---

## Le principe, en une page

L'axiome de l'outil s'énonce simplement :

> **Deux situations qui s'écrivent avec les mêmes lettres ont le même avenir probable.**

C'est une hypothèse, pas une évidence. Elle dit que la **forme** d'une situation — un seuil, une
polarité, une contrainte, une trace — en dit plus sur ce qui va suivre que son domaine : une crise
géopolitique et une crise financière qui partagent les mêmes formes devraient évoluer de la même
manière. C'est ambitieux, et c'est testable. Tout le reste de l'outil est construit pour rendre ce test
possible, et pour l'empêcher de tricher.

Deux conséquences, qui expliquent toute l'architecture :

- **Il faut un vocabulaire fermé.** Si chacun invente ses mots, deux situations ne peuvent jamais
  s'écrire « avec les mêmes lettres ». D'où les seize cartes, et les treize domaines dans lesquels
  chacune se traduit.
- **Il faut une mémoire de cas.** Sans cas passés écrits de la même façon, l'hypothèse ne dit rien. D'où
  la base de cas, le journal des paris et le score.

Le dépôt appelle cela « prévision par homologie structurelle ». Retenez seulement : **on ne compare pas
des histoires, on compare des formes.**

---

# Partie I · La moitié sémiotique

> Comment un fait devient un signe, et un signe une lettre.

## 1. Qu'est-ce qu'un signe, ici ?

Un signe n'est pas un mot. C'est un **fait observable qui remplit une case**. L'outil ne lit pas des
opinions, des ambiances ou des intentions : il lit des faits datés, et il vérifie qu'ils cochent un
marqueur précis.

Prenons l'exemple qui sert de fil rouge dans toute la note : un pays A plafonne un prix, un pays B
annonce des représailles.

- « Le pays A a plafonné le prix du gaz le 12 septembre » est un **fait**.
- Ce fait remplit le marqueur de la carte **CONTRAINTE** : il réduit l'ensemble des états possibles pour
  les acteurs. C'est un **signe**.
- « Les représailles annoncées par B » remplissent le marqueur de la carte **POLARITÉ** : la relation
  s'est tendue selon un axe à deux pôles. C'est un second **signe**.

La phrase qui en résulte est l'**état** de la situation :

```
[2026-09 | 3 mois] POLARITÉ@7[F] + CONTRAINTE@6[F]
```

Lisez-la à voix haute : « en septembre 2026, sur une fenêtre de trois mois, une polarité géopolitique
forte et une contrainte économique forte sont ancrées ». Le `7` et le `6` sont les domaines — ici la
géopolitique et l'économie. Le `F` dit la qualité de l'ancrage, nous y reviendrons.

Rien là-dedans n'est un score, un vecteur de trois cents dimensions ou une opinion cachée. C'est une
phrase, datée, qu'un autre lecteur peut contester.

## 2. Les trois étages : fait, marqueur, carte

Un signe se construit en trois temps, et l'ordre compte.

| Étage | Question posée | Exemple |
|---|---|---|
| **Le fait** | Que s'est-il passé, où, quand, selon quelle source ? | le plafond de prix du 12 septembre |
| **Le marqueur** | Quelle observation précise ce fait coche-t-il ? | « l'ensemble des états possibles est réduit » |
| **La carte** | Quelle forme générale ce marqueur traduit-il ? | CONTRAINTE |

L'étape du milieu est celle qu'on saute quand on veut se convaincre trop vite. Sans elle, on ne lit pas
des signes : on reconnaît des thèmes. « Parler d'économie » n'est pas un signe de contrainte ; « un
plafond de prix » en est un, parce qu'il change ce que les acteurs peuvent faire.

C'est pourquoi le même fait ne peut ancrer qu'**une carte par domaine**. Un fait peut concerner
plusieurs domaines — une sanction est un fait géopolitique qui a des effets économiques — mais il faut
alors **deux faits**, un par domaine, et non un seul mot utilisé deux fois pour faire bonne mesure.

## 3. Pourquoi tous les signes ne se valent pas : les quatre tests

Un fait qui coche un marqueur n'est pas encore une preuve. L'outil reprend une distinction classique de
l'histoire et des sciences sociales, qu'on peut expliquer avec une métaphore judiciaire.

| Test | Image | Ce qu'il établit |
|---|---|---|
| **La paille** | un indice compatible avec l'hypothèse | presque rien : beaucoup d'histoires sont compatibles avec beaucoup d'indices |
| **Le cerceau** | une condition nécessaire, mais pas suffisante | que l'hypothèse doit être vraie, sans garantir qu'elle le soit |
| **Le pistolet fumant** | un fait qui suffit à établir l'hypothèse | beaucoup, à lui seul |
| **Le doublement décisif** | un fait qui établit l'hypothèse **et** écarte la rivale | le maximum |

La force `F` n'est pas « je suis sûr ». Elle exige un **pistolet fumant** ou un **doublement décisif**.
Si le fait remplit le marqueur sans être suffisant, c'est `f`. Cette distinction est le cœur de la
discipline : elle empêche de confondre « le fait est vrai » et « le fait prouve ce qu'on lui fait dire ».

À quoi s'ajoutent trois exigences, qui portent des noms mais sont simples :

- **la garantie** : dire par quel mécanisme ce fait produit cet effet, ce qu'on s'attendrait à observer,
  et ce qui contredirait la lecture ;
- **l'option** : le fait doit changer l'espace d'action de quelqu'un. Un événement qui ne change rien
  pour personne n'est pas un signe, c'est un décor ;
- **le passage** : citer le texte qui soutient le fait **tel qu'il est écrit**. Une annonce ne prouve
  pas une réalisation ; « pourra être activé » ne soutient pas « a été activé ».

## 4. F et f : une qualité, jamais une intensité

C'est la confusion la plus fréquente, et elle fausse tout le reste.

`F` et `f` mesurent la **qualité de la preuve d'ancrage**. Ils ne mesurent pas la force du phénomène.
Un seuil peut être `F` et concerner un petit marché ; une polarité peut être `f` et concerner deux
grandes puissances. Le `F` dit : « les pièces sont là, et elles sont décisives ». Le `f` dit : « le
marqueur est rempli, mais la preuve reste faible ».

Cette qualité n'entre **pas** dans les multiplicateurs du calcul. Un ancrage `F` ne rend pas un
coefficient plus fort. Il entre dans le calcul par une autre porte : il aide à choisir les cas passés
qui ressemblent le plus à la situation présente. Nous y reviendrons en partie III, parce que c'est
là que la couture entre les deux moitiés devient visible.

## 5. Chercher la contradiction, pas la confirmation

Un lecteur sérieux ne cherche pas ce qui confirme sa lecture : il cherche **la meilleure objection**.
L'outil appelle cela l'anti-résonance, et il impose trois familles de recherches par carte :

1. **l'observation** : que montrent les sources sur ce point précis ?
2. **la discrimination** : qu'est-ce qui distingue cette carte d'une carte rivale ?
3. **la contradiction** : quel fait, dans la situation, va contre la lecture ?

Puis on classe la portée de ce qu'on trouve : **marginale** (rien ne bouge), **substantielle** (la force
descend de `F` à `f`), **dominante** (la lecture est rejetée). Un rejet est un résultat normal. C'est
même le signe que la procédure fonctionne : un dispositif qui ne rejette jamais ne lit rien, il confirme.

Depuis la version 0.7.4, cette recherche a un **plancher vérifiable** : trois familles par carte de
l'état, une discrimination par paire de candidates d'un même domaine, et les requêtes consignées. Une
requête répétée ne compte qu'une fois ; une requête construite avec le nom de la carte est signalée,
parce qu'elle trouvera surtout ce qu'on lui a demandé de trouver.

## 6. Ce que la lecture produit : une phrase, pas un chiffre

À la fin de la phase de lecture, on obtient trois choses :

- **un état daté** : la phrase du §1 ;
- **des candidates rejetées**, avec le motif de leur rejet — y compris une rivale jamais ancrée, ce qui
  évite de fabriquer une contre-candidate de complaisance ;
- **un dossier de lecture** : l'ensemble des pièces (faits, preuves, requêtes, questions, définition de
  l'événement), assemblé et **scellé avant le calcul**.

Ce dossier est la grande idée de la version 0.7.3. Avant lui, la discipline de preuve existait pour les
fiches historiques, mais pas pour la lecture qui produit une probabilité — c'est-à-dire pas là où elle
comptait le plus. Le sceau rend la lecture relisible par un tiers qui n'a pas assisté au calcul. C'est
aussi ce qui permet un second codeur, et donc la mesure de l'accord entre deux lecteurs.

## 7. Ce que la sémiotique ne fait pas

Elle ne produit aucun nombre. Elle ne dit jamais « il y a 22 % de chances ». Elle dit : « voici les
formes présentes, voici la qualité de leur ancrage, voici ce qui les contredirait ». Si aucune carte
n'atteint la force `f`, l'état est **nul** : l'outil le déclare et ne prévoit rien. Ce n'est pas un
échec, c'est une issue prévue.

---

# Partie II · La moitié mathématique

> Comment des lettres deviennent une fréquence, et ce que cette fréquence garantit — ou non.

## 1. Ce que reçoit le calculateur

Le calculateur ne voit pas le monde. Il reçoit :

- un **état** : des cartes, des forces, une date et une fenêtre ;
- un **événement** à prévoir, défini à l'avance, avec une échéance ;
- une **base de cas** : des situations passées, écrites avec le même alphabet, dont on sait ce qui est
  arrivé ;
- éventuellement une **fréquence de base externe** : à quelle fréquence ce type d'événement se produit
  dans ce domaine.

Si l'état est nul, il n'y a rien à calculer. Si l'événement n'est pas défini, il n'y a rien à scorer.
Toute la mathématique est donc **conditionnée par la qualité de ce qu'on lui donne** : c'est le point
de la partie III.

## 2. La fréquence de base, et la prudence des vingt témoins

Le point de départ est une fréquence : « ce type d'événement arrive environ tant de fois sur trois
mois ». Par défaut, l'outil prend **5 %** — une valeur prudente, pas une mesure.

Cette fréquence est ensuite **lissée** vers une référence par vingt pseudo-observations. L'image utile
est celle d'un témoin virtuel qui pèserait vingt cas. Si vous avez trois cas réels, le témoin parle plus
fort qu'eux ; si vous en avez cinquante, ce sont les cas qui parlent.

C'est ce que veut dire « **ancré** » depuis la version 0.7.7 : les données pèsent au moins autant que
la référence (vingt observations pondérées). En dessous, le chiffre est **publié** — on peut le lire —
mais il n'est pas **ancré** — on ne peut pas s'appuyer dessus. La distinction paraît technique ; elle
ne l'est pas. Elle sépare « voici un nombre » de « voici un nombre qui vaut quelque chose ».

## 3. Les multiplicateurs : des paris, pas des mesures

Chaque carte présente apporte un **multiplicateur** :

- `3,0` pour un lien fort dans la matrice ;
- `1,8` pour un lien moyen ;
- `1,2` pour un lien faible.

Ces nombres ne sont pas mesurés sur des données. Ce sont des **hypothèses de travail**, inscrites dans
une matrice de 66 liens entre les 16 cartes. Trois seulement sont forts. Autrement dit : la théorie
interne de l'outil est majoritairement faite de liens faibles, et elle le sait.

Le calcul combine ces multiplicateurs avec la fréquence de base pour obtenir un **a priori** `p₀`. On
peut le voir comme une recette : plus de cartes actives, plus le a priori s'écarte de la fréquence
générale — mais jamais au-delà d'un plafond (le produit des multiplicateurs est limité à 10). Ce
plafond est une soupape : sans lui, cinq cartes suffiraient à produire une certitude.

## 4. La révision par les cas : chaque homologue est un vote

Vient ensuite la partie la plus intéressante. L'outil cherche dans la base les situations **écrites avec
les mêmes lettres** — les « homologues » — et regarde ce qui leur est arrivé.

La formule est une moyenne pondérée :

```
p = (nombre d'événements observés + 2 × p₀) / (nombre de cas + 2)
```

Le `2` est le poids du a priori, exprimé en cas. Dix cas homologues pèsent donc cinq fois plus que
l'a priori. Trois cas pèsent à peine plus. C'est volontairement conservateur : l'outil ne croit pas
qu'un cas isolé fasse une règle.

Deux précisions importantes :

- **les cas ne sont pas égaux.** Dix cas peuvent valoir 9,3 observations effectives si l'un d'eux pèse
  beaucoup plus lourd (16 % du total dans la démonstration). C'est la taille effective de Kish, et elle
  est publiée ;
- **les homologues ne sont pas tous aussi proches.** L'outil distingue les cas qui partagent exactement
  les mêmes cartes (H1), ceux qui en partagent une grande partie (H1.5, similarité ≥ 0,7), et ceux qui
  viennent d'un autre domaine (H2). Le niveau retenu est publié, avec sa fragilité.

## 5. L'intervalle et le niveau de risque

Le résultat n'est pas un chiffre unique. C'est un **chiffre avec un intervalle** : dans la
démonstration, 22,0 % [5,2–43,1]. L'intervalle est large, et il doit l'être : peu de cas, beaucoup
d'incertitude.

À quoi s'ajoute un **niveau** ρ0 à ρ4, qui ne dit pas la fiabilité mais **la provenance** :

| Niveau | D'où vient le chiffre |
|---|---|
| **ρ0** | au moins 30 cas homologues distincts dans le domaine, avec double codage |
| **ρ1** | 3 à 29 cas homologues distincts |
| **ρ2** | au moins 3 cas empruntés à un autre domaine |
| **ρ3** | aucun cas, mais un a priori structurel **ancré** |
| **ρ4** | a priori non ancré, lecture symbolique, intuition, état nul |

Un chiffre ρ1 peut être excellent ; un chiffre ρ3 peut être juste. Mais le lecteur doit savoir que le
second ne repose sur aucun cas. C'est une échelle de **traçabilité**, pas de qualité.

## 6. Les garde-fous : six façons de ne pas se mentir

C'est la partie la plus originale de l'outil, et la plus facile à sous-estimer. À chaque prévision
s'ajoutent des calculs qui ne servent pas à prévoir, mais à savoir **ce que le chiffre doit à quoi**.

| Garde-fou | La question qu'il pose |
|---|---|
| **Comparateur sans cartes** | que vaudrait la même prévision sans aucune carte, avec la seule inertie ? |
| **Bande de modèle** | combien le chiffre bouge si les multiplicateurs, les inerties ou la fréquence par défaut varient d'un cran ? |
| **Bande de classe** | combien il bouge si l'on change le seuil de similarité, le lissage ou la demi-vie des cas ? |
| **Placebo d'homologie** | combien il bouge si l'on remplace les cas choisis par autant de cas tirés au hasard ? |
| **Confrontation** | les transitions observées sont-elles seulement **atteignables** par la matrice ? |
| **Sonde** | la matrice réelle fait-elle mieux que des matrices tirées au hasard ? |

Les quatre premiers mesurent la **robustesse du réglage et du choix des cas**. Les deux derniers mesurent
le **contenu de la matrice**. La distinction est décisive : une bande étroite dit « mon réglage est
stable », pas « mes catégories sont bonnes ». Et un placebo favorable dit « mes cas ressemblent à quelque
chose », pas « mes arêtes sont vraies ».

## 7. Le score, et le jalon V4

À l'échéance, chaque pari est **scoré**. Le score principal est le **Brier** : la moyenne des carrés des
écarts entre la probabilité annoncée et l'issue (0 = parfait, 0,25 = hasard sur une question binaire
équilibrée). Un score logarithmique est publié en regard, plus sensible aux erreurs confiantes.

Le jalon de validation, appelé **V4**, a changé de définition en 0.7.7. Il ne dit plus « 10 % de mieux
sur 50 épisodes », mais :

- la perte moyenne par épisode doit baisser d'au moins **2,5 points** ;
- le **test du signe** doit être significatif à 5 % — autrement dit, les épisodes améliorés doivent
  être plus nombreux que les épisodes dégradés, et pas seulement en moyenne ;
- le nombre d'épisodes doit atteindre **max(50, l'effectif calculé à partir de l'écart-type observé)**.

La dernière ligne est la plus importante. Cinquante épisodes ne suffisent que si l'écart-type des écarts
ne dépasse pas 0,063. Au-delà, il en faut davantage — parfois beaucoup plus. Une règle qui calcule son
propre effectif ne peut pas être franchie avec trois épisodes favorables : elle oblige à accumuler les
cas avant de conclure.

## 8. Ce que les mathématiques ne font pas

Elles ne prouvent pas la causalité. Le moteur ne répond ni à « que produirait telle action ? » ni à « que
se serait-il passé autrement ? ». Il calcule une association, et le dit : barreau A de l'échelle de
Pearl.

Elles ne certifient pas la matrice. Une matrice cohérente, stable et non aléatoire peut être
systématiquement fausse : elle ne se trompe pas au hasard, elle se trompe de façon stable. Aucune
quantité de données ne corrige un vocabulaire mal choisi.

Elles ne remplacent pas la lecture. Sans état, sans événement défini, sans dossier, le calcul produit un
chiffre sur du vide — et le drapeau le dit.

---

# Partie III · Comment l'une conditionne l'autre

> Le fil. C'est la partie qu'il faut retenir si l'on ne retient qu'une chose.

## 1. La chaîne complète

```
un fait daté
    ↓  (marqueur rempli)
un signe, avec une force F ou f
    ↓  (une carte par domaine)
un état daté : « POLARITÉ@7[F] + CONTRAINTE@6[F] »
    ↓  (recherche des cas écrits de la même façon)
une classe d'homologues
    ↓  (matrice + fréquence de base + révision)
une probabilité p, un intervalle, un niveau ρ
    ↓  (à l'échéance)
un score, qui juge la lecture
    ↓
retour à la lecture : garder, réviser ou rejeter
```

Chaque flèche est un **conditionnement**. Si une flèche casse, tout ce qui suit est faux, et le plus
souvent silencieusement faux.

## 2. Première loi : sans signe, pas de nombre

Le calculateur ne peut pas inventer un état. Si aucune carte n'atteint `f`, l'état est nul et l'outil
**ne prévoit rien**. Il ne dit pas « 0 % » : il dit « non estimé ». La différence est capitale. Un zéro
est une affirmation ; « non estimé » est un aveu.

C'est le premier conditionnement, et le plus radical : **la sémiotique a un droit de veto sur la
mathématique**. Un fait mal daté, un marqueur non coché, une preuve insuffisante, et le calcul n'a plus
d'entrée. L'outil préfère se taire plutôt que de calculer sur une lecture qu'il n'a pas contrôlée.

## 3. Deuxième loi : le signe choisit les nombres, il ne les fabrique pas

Une fois l'état écrit, les cartes présentes décident **quels** multiplicateurs s'appliquent. Mais les
valeurs de ces multiplicateurs viennent de la **matrice**, pas de la force `F` ou `f`.

Autrement dit :

- le lecteur dit **quelles** formes sont là ;
- la matrice dit **combien** chacune pèse ;
- la force dit **à quel point** la présence de la forme est bien établie.

Trois rôles distincts, trois sources distinctes. C'est pourquoi un `F` ne rend pas un coefficient plus
fort. Si l'on confond les trois, on croit qu'une lecture plus assurée produit mécaniquement un chiffre
plus élevé — ce qui est faux, et ce que le dépôt corrige explicitement depuis 0.7.3.

## 4. Troisième loi : le signe entre deux fois, mais pas au même endroit

La force `F`/`f` entre tout de même dans le calcul, par une autre porte : elle sert à **choisir les
homologues**. Deux cas qui partagent exactement les mêmes cartes avec les mêmes forces sont plus
proches que deux cas qui partagent les mêmes cartes avec des forces différentes. La force aide donc à
construire la classe de référence.

C'est le point le plus subtil du dispositif. Il y a deux canaux possibles pour la qualité de l'ancrage :

1. **la sélection des cas** — canal actif, mesuré, intégré au calcul ;
2. **l'atténuation des multiplicateurs** — canal proposé, aujourd'hui calculé **hors** du `p` publié.

Pourquoi ne pas activer le second ? Parce que les deux canaux sont partiellement colinéaires : si l'on
abaisse un coefficient **et** que l'on change les cas retenus, on ne sait plus lequel fait le travail,
et l'on risque de compter deux fois la même confiance. La version 0.7.6 a donc mesuré l'atténuation
comme variante ; la version 0.7.7 a écrit la règle de promotion **avant** les données : à vingt cas
double-codés, une seule variante passera au défaut, et seulement si son gain est significatif.

C'est un exemple parfait de la couture : la sémiotique réclame que la qualité de la preuve pèse ; la
mathématique répond « d'accord, mais prouve-le, et pas deux fois ».

## 5. Quatrième loi : le calcul juge la lecture, et peut la renvoyer

C'est le conditionnement inverse, et c'est celui qui rend l'outil falsifiable.

- Le **placebo** demande : « vos cas choisis font-ils mieux que des cas tirés au hasard ? ». Si non, le
  chiffre vient de l'a priori et du domaine, pas de l'analogie.
- La **sonde** demande : « votre matrice fait-elle mieux que des matrices aléatoires ? ». Si non, elle
  n'a pas de contenu propre à défendre.
- La **confrontation** demande : « vos transitions observées sont-elles seulement atteignables par la
  matrice ? ». Sur les cas archivés, deux apparitions sur trois ne le sont pas.
- **V4** demande : « vos prévisions battent-elles l'inertie, de manière significative, sur assez
  d'épisodes ? ».

Chacun de ces dispositifs peut dire non. Et un non n'est pas un échec : c'est une information qui
renvoie à la lecture — réviser un marqueur, changer une carte, documenter une lacune.

C'est ici que la boucle se ferme. La sémiotique produit des signes ; la mathématique les met à
l'épreuve ; le résultat de l'épreuve revient modifier la sémiotique. Un outil qui ne ferait pas ce
retour ne serait pas un instrument, seulement une typologie.

## 6. Cinquième loi : la mathématique impose sa forme à la lecture

On oublie souvent ce sens-là. Pour qu'un chiffre soit **scorable**, il faut :

- un événement défini à l'avance, avec une échéance ;
- une source de résolution qui mesure bien le marqueur local, et pas un phénomène voisin ;
- une sémantique déclarée : l'événement doit être « présent à la fin », « présent au moins une fois »
  ou « présent en continu » — ce n'est pas la même question ;
- une date d'information, pour ne pas utiliser des cas postérieurs ;
- un dossier scellé, pour que la lecture soit antérieure au chiffre ;
- des requêtes consignées, pour que « j'ai cherché » soit constatable.

Autrement dit, **la mathématique contraint la sémiotique** : elle lui interdit les lectures qui ne
pourraient pas être jugées. Un lecteur qui refuse de dater, de définir ou de sceller ne peut pas
produire de pari ; il produit une opinion. La discipline du calcul remonte donc dans la discipline de
lecture, et c'est peut-être son effet le plus utile.

## 7. Ce que le calcul ne peut pas corriger

Il ne peut pas corriger un **vocabulaire systématiquement biaisé**. Si la carte SEUIL est définie de
telle façon qu'elle attrape toutes les ruptures, elle en attrapera aussi qui n'en sont pas, et les
chiffres seront stables, cohérents et faux. Les garde-fous mesurent la robustesse et le contenu, pas la
validité du découpage.

Il ne peut pas non plus remplacer le **jugement sur les faits**. Une source fausse produit un signe
faux, un état faux, un chiffre faux — et le score ne le verra que si l'événement se réalise ou non. La
qualité de la lecture reste une **condition préalable**, pas une sortie du système.

C'est pourquoi la note insiste tant sur le second codeur : sans lui, on ne mesure pas la fiabilité de la
lecture, on mesure seulement sa cohérence interne.

---

## Un exemple complet, pas à pas

Reprenons le fil rouge, en marquant à chaque étape quelle moitié travaille.

| Étape | Ce qui se passe | Moitié |
|---|---|---|
| 1 | Un plafond de prix est promulgué le 12 septembre ; le texte est cité. | sémiotique |
| 2 | Le fait remplit le marqueur de CONTRAINTE ; la preuve est un pistolet fumant → `F`. | sémiotique |
| 3 | Des représailles sont annoncées et exécutées ; POLARITÉ@7 → `F`. | sémiotique |
| 4 | L'état est écrit : `[2026-09 \| 3 mois] POLARITÉ@7[F] + CONTRAINTE@6[F]`. | sémiotique |
| 5 | L'événement est défini : « SEUIL@7 apparait », avec sa source de résolution. | sémiotique, contrainte par le calcul |
| 6 | Le dossier est scellé ; la probabilité personnelle est écrite avant le moteur. | sémiotique |
| 7 | Le moteur cherche 10 cas homologues (H1) et calcule `p = 22,0 %`. | mathématique |
| 8 | Il publie l'intervalle [5,2–43,1], le niveau ρ1, la bande de modèle 19–28 %, la bande de classe 21–23 %. | mathématique |
| 9 | Il publie le placebo 20,2 % et l'apport de l'homologie +1,8 point. | mathématique |
| 10 | Il refuse de lire l'écart aux cartes (+10 points) comme un effet : l'a priori n'est pas ancré. | mathématique, qui déclare la limite |
| 11 | À l'échéance, le Brier est calculé ; le pari est conservé, jamais réécrit. | mathématique |
| 12 | Si V4 échoue, la lecture des cartes sera révisée. | retour à la sémiotique |

Ce tableau est le résumé de tout le document. Les étapes 1 à 6 sont des jugements sur des signes ; les
étapes 7 à 11 sont des calculs ; l'étape 12 est le retour du calcul vers les signes.

---

## Quatre confusions à éviter

**1. « F veut dire fort. »** Non. `F` veut dire « la preuve de l'ancrage est suffisante ». Un fait
`F` peut concerner un phénomène modeste. La force d'un phénomène n'est pas mesurée par l'outil ; elle
n'est même pas une grandeur qu'il prétend représenter.

**2. « 22 %, c'est la probabilité que ça arrive. »** Non. C'est une fréquence conditionnelle
expérimentale, calculée à partir d'une matrice postulée et de cas choisis. Le niveau ρ1 dit qu'elle
repose sur 10 cas ; l'intervalle dit qu'elle est fragile ; le barreau A dit qu'elle n'est pas causale.
Elle se lit : « si le motif observé se répète, alors cette fréquence ».

**3. « Non estimé, c'est zéro. »** Non. « Non estimé » veut dire que l'outil n'a pas d'entrée
suffisante pour calculer. C'est une position honnête, et c'est souvent la plus informative : elle dit
où la lecture doit progresser.

**4. « Publié, c'est ancré. »** Non, depuis 0.7.7 précisément. Un comparateur peut être publié dès un
cas et rester non ancré : il est alors affiché, mais l'écart qu'il produit n'est pas interprétable. La
distinction entre « disponible » et « fondé » est l'une des corrections les plus utiles de la version.

---

## Ce qu'il faut retenir

L'Alphabet situationnel n'est pas un oracle. C'est une **discipline de lecture** à laquelle on a attaché
un **calculateur** et un **juge**.

- La partie sémiotique décide **ce qui compte comme signe**. Elle est lente, coûteuse, contestable — et
  c'est elle qui porte tout le reste.
- La partie mathématique décide **ce que valent ces signes**, en les comparant à des cas, à l'inertie,
  au hasard et à elle-même.
- Le conditionnement est double : **sans signe, pas de nombre** ; **sans nombre, pas de jugement sur le
  signe**. C'est cet aller-retour qui distingue un instrument d'une typologie.

Aujourd'hui, l'outil a une méthode complète et **zéro cas réel actif**. Sa valeur actuelle n'est donc
pas dans ses prédictions : elle est dans sa capacité à dire ce qu'un chiffre doit à quoi, et à refuser
de conclure quand il ne le peut pas. C'est peu spectaculaire. C'est rare.

---

*Document de vulgarisation de la note « Lire le langage, prévoir l'événement », version 0.7.7,
révision 1, 30 octobre 2026. Les chiffres cités proviennent de la base de démonstration
**entièrement fictive** du dépôt analysé : ils illustrent une mécanique, jamais une performance. Aucune
performance prédictive n'est acquise.*
