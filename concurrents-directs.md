# Les concurrents directs de l'Alphabet situationnel

### Ce qui occupe la même place — et ce que cela oblige à prouver

**Document de comparaison · version 0.7.15 · révision 1 · 31 octobre 2026**

Dépôt analysé : `Othman-Benbrahim/alphabet-situationnel` · version 0.7.15 · licence MIT

> **Objet.** Ce document répond à une question que la note principale laissait ouverte : à quoi
> l'Alphabet situationnel est-il **directement** comparable ? Il distingue les rivaux qui prétendent
> occuper la même place — lire une situation par une grammaire transversale et en tirer une
> conséquence utilisable — des méthodes adjacentes qui font autre chose, et des cadres de calcul qui
> ne disent rien de la vérité des modèles construits avec eux.
>
> **Statut.** Document de comparaison, pas d'importation. Aucune ligne ne propose un changement de
> règle du dépôt analysé ; les épreuves proposées sont des protocoles, pas des fonctionnalités.
>
> **Méthode.** Sources lues entre le 30 et le 31 octobre 2026, listées en §10. Les chiffres de
> performance sont ceux que publient les opérateurs ou les évaluateurs indépendants, avec leur date.
> Les affirmations qui n'ont pas été vérifiées sur un texte primaire sont signalées comme telles.
>
> **Une révision de périmètre.** La première rédaction de ce document retenait sept rivaux, tous issus
> de la stratégie, du management ou de l'ingénierie. Un audit versé par l'auteur le 31 octobre 2026
> (ciblant la version 0.7.11) a montré que le concurrent le plus proche n'est pas là : il est en
> **sociologie relationnelle**, avec *Dynamics of Contention*. Quatre rivaux disciplinaires (cliodynamique,
> panarchie, théorie des catastrophes, DoC) et deux instruments (QCA, inférence séquentielle) ont été
> ajoutés en conséquence. Ce que l'audit établit et ce que le dépôt en a fait sont récapitulés en §6.4.

---

## 1. Ce que « concurrent direct » veut dire

Trois conditions, et il faut les trois :

1. **Même promesse.** L'instrument prétend dire quelque chose d'une situation qui ne dépende pas
   seulement de son domaine : une forme, une structure, un mécanisme, une issue.
2. **Même usage.** Un lecteur peut s'en servir pour **juger** ou **décider**, pas seulement pour
   décrire après coup.
3. **Même exigence de preuve.** Il existe une manière de le prendre en défaut — un cas, un score, un
   désaccord entre codeurs, une prévision datée.

Une méthode qui remplit les deux premières conditions mais pas la troisième est un **vocabulaire**,
pas un concurrent. Une méthode qui remplit la troisième mais pas la première est un **outil de
mesure**, pas un concurrent. C'est cette distinction qui permet de ne pas confondre Wardley avec
pgmpy, ou Cynefin avec un tableur.

Le champ s'organise alors en quatre cercles de concurrents — **seize rivaux, plus sept instruments de
calcul** — et un cercle d'alliés dont aucun ne prétend occuper la même place :

| Cercle | Ce qu'on y trouve | Rapport à l'Alphabet |
|---|---|---|
| **Rivaux de même promesse** | Wardley, Cynefin, MACTOR, ACH, analyse morphologique, scénarios, Bueno de Mesquita | désaccord sur ce qui est prévisible, sur ce qu'on a le droit de nommer, ou sur la forme de la preuve |
| **Rivaux disciplinaires** | cliodynamique (Turchin), panarchie (Holling), théorie des catastrophes (Thom, Zeeman), *Dynamics of Contention* (McAdam, Tarrow, Tilly) | même objet, même ambition transversale, mais dans une discipline constituée — et, pour l'un d'eux, une prédiction datée déjà publiée |
| **Concurrents de la chaîne de prévision** | CAMEO/GDELT/POLECAT, ViEWS, superforecasters, marchés de prédiction, prévisionnistes LLM | même chaîne texte → état → pari, autre unité de codage et autre classe de référence |
| **Cadres de calcul et instruments** | PyCIB, FCMpy, pgmpy, EMA Workbench, `forecasting-tools`, QCA (Ragin), CIB (Weimer-Jehle) | ne prétendent pas lire la situation ; ils calculent ce qu'on leur donne, ou mesurent la qualité d'une règle |
| **Alliés et contradicteurs théoriques** | Green & Armstrong, Tetlock, Toulmin, Gentner, Sood & Gelman, Howard & Ramdas | apportent des contrôles ou une objection précise, pas une ontologie concurrente |

---

## 2. Le tableau de synthèse

| Concurrent | Ce qu'il promet | Ce qu'il produit | Preuve publique | Écart décisif avec l'Alphabet |
|---|---|---|---|---|
| **Wardley Mapping** | la **direction** du mouvement de tout composant, vers la commodité | une carte valeur × évolution, quatre stades, 40 principes de doctrine | usage industriel vaste ; pas de score de justesse | l'Alphabet nie une loi de transition unique (P1) et produit des dates et un score ; Wardley produit une direction sans horloge |
| **Cynefin** | le **domaine** d'une situation, donc la méthode appropriée | cinq domaines, quatre contraintes, des dynamiques de passage | cadre très diffusé ; peu de mesures d'accord inter-codeurs | l'Alphabet parie sur une transition conditionnelle ; Cynefin nie la prévision dans le complexe et prescrit de sonder |
| **MACTOR** | les **rapports de force** et les convergences entre acteurs | matrice acteurs × objectifs, influences 0–4, coalitions | méthode de prospective diffusée depuis 1989 ; pas de score prospectif publié | l'Alphabet lit des structures, pas des acteurs ; MACTOR modélise ce que l'Alphabet nomme seulement (INCERTITUDE) |
| **ACH** | la **hypothèse la moins réfutée** | matrice hypothèses × preuves, cohérent/incohérent/neutre | pratique analytique standard du renseignement ; pas de score | l'Alphabet produit une probabilité et une classe de référence ; ACH produit un classement qualitatif et une trace de raisonnement |
| **Analyse morphologique (GMA)** | l'**espace complet** des configurations cohérentes | paramètres × valeurs, évaluation de cohérence croisée | méthode formalisée depuis Zwicky ; usage en planification | l'Alphabet a un vocabulaire fermé et un moteur probabiliste ; GMA a un espace de configurations et pas de probabilité |
| **Scénarios (Shell/GBN)** | des **futurs alternatifs** pour éprouver une décision | 2 × 2 ou récits, éléments prédéterminés et incertitudes critiques | pratique de long terme ; pas de score de justesse | l'Alphabet produit un chiffre pour un événement défini ; les scénarios ne sont pas des prévisions |
| **Bueno de Mesquita** | l'**issue** d'une négociation entre acteurs identifiés | équilibres bayésiens parfaits, positions, saillance, capacité, flexibilité | revendications fortes (Feder) ; modèle non public ; réplication ouverte 2026 défavorable | l'Alphabet ne nomme pas les acteurs et ne résout pas un jeu ; il parie sur une transition de structure |
| **CAMEO / GDELT / POLECAT** | coder **qui fait quoi à qui** | millions d'événements datés, géolocalisés, typés | backtests nombreux ; GDELT très rappel, POLECAT plus précis | l'Alphabet code des structures, pas des actes ; il perd l'échelle, il gagne l'interprétabilité |
| **ViEWS** | la **probabilité et l'intensité** de conflit armé | prévisions pays-mois et grille 0,5°, 1–36 mois | système opérationnel, données ouvertes, évaluation continue | l'Alphabet est trans-domaines et qualitatif ; ViEWS est mono-domaine et quantitatif |
| **Superforecasters** | une **probabilité calibrée** sur des questions résolues | jugement agrégé, Brier, track record | 831 questions résolues au 6 août 2026 ; 79 % de victoires contre les équipes hybrides | l'Alphabet impose une ontologie et une classe de référence ; les superforecasters laissent le jugement choisir ses catégories |
| **Marchés de prédiction** | le **prix** d'un contrat sur un événement | probabilité implicite, liquidité, historique | comparaisons nombreuses ; Polymarket battu par les superforecasters sur les banques centrales | l'Alphabet n'a pas de prix ni de liquidité ; il a une trace de lecture |
| **Prévisionnistes LLM** | une **probabilité** sur des questions ouvertes, à grande échelle | bot + recherche + agrégation | ForecastBench, FutureEval, Prophet Arena | l'Alphabet est un protocole de lecture ; les bots sont un moteur de synthèse sans ontologie fixe |
| **Cliodynamique** (Turchin) | les **cycles** d'instabilité politique, par la démographie et les élites | modèle structure-démographique, indicateur de stress politique | **une prédiction datée et publiée** (2010), réévaluée en 2020 par ses auteurs | l'Alphabet a un modèle nul et un score ; Turchin a un fait accompli et pas de modèle nul explicite |
| **Panarchie** (Holling) | le **cycle adaptatif** r → K → α → Ω, emboîté | quatre phases, résilience, connectivité, potentiel | littérature écologique vaste ; les auteurs eux-mêmes demandent « plus qu'une métaphore ? » | l'Alphabet est **décomposable** : une carte peut être Vide sans invalider les quinze autres |
| **Théorie des catastrophes** (Thom, Zeeman) | la **discontinuité** : hystérésis, bistabilité, fronce | surfaces de catastrophe, paramètres de contrôle | programme critiqué et largement abandonné en sciences sociales (Sussmann & Zahler) | SEUIL *est* une fronce ; l'Alphabet y ajoute le **marqueur local indépendant du modèle** qui manquait |
| ***Dynamics of Contention*** (McAdam, Tarrow, Tilly) | des **mécanismes transposables** entre épisodes | courtage, formation de catégories, défection des élites, etc. | 18 épisodes comparés ; communauté empirique large | l'Alphabet ajoute la **dimension de strate** et un chiffre ; DoC ajoute la comparabilité inter-épisodes |
| **QCA** (Ragin) | la **consistance et la couverture** d'une règle configuration → issue | table de vérité, paramètres d'ajustement | méthode établie, logiciels mûrs | l'Alphabet a des configurations et des issues, mais aucun équivalent de *consistency* ni de *coverage* |
| **Inférence séquentielle** (Howard, Ramdas) | des intervalles **valides à tout instant** | suites de confiance, e-processus, p-processus | statistique publiée, non asymptotique | l'Alphabet teste à effectif fixe sur un journal croissant : le remplacement est en place depuis 0.7.12 (`e_processus`) |
| **PyCIB / FCMpy / pgmpy / EMA** | calculer les **conséquences** d'un modèle | scénarios cohérents, simulations, inférence | bibliothèques logicielles, tests, publications | ils ne disent rien de la vérité du modèle ; l'Alphabet est un modèle, pas un solveur |

---

## 3. Les rivaux de même promesse

### 3.1 Wardley Mapping — le plus proche par la forme

**L'appareil.** Deux axes : une **chaîne de valeur** ancrée sur un besoin d'usager, et une
**évolution** en quatre stades — *genesis*, *custom built*, *product*, *commodity*. Quatre types de
composants se placent sur cet axe : activités, pratiques, données, connaissances. Trois couches :
**climat** (les forces qu'on ne choisit pas), **doctrine** (quarante principes réputés universels),
**gameplay** (les coups propres au contexte). Le corpus est accessible sur
[learnwardleymapping.com](https://learnwardleymapping.com/doctrine/) et dans les écrits de Simon
Wardley.

**La thèse.** Tout composant évolue de la gauche vers la droite sous la pression de la concurrence :
« everything evolves through supply and demand competition », « no choice over evolution ». La
direction serait prévisible ; le **moment** ne le serait pas. Wardley l'écrit explicitement :
« You cannot measure evolution over time or adoption »
([Wardley Leadership Strategies](https://www.wardleyleadershipstrategies.com/climatic-patterns/you-cannot-measure-evolution-over-time-or-adoption-you-need-to-embrace-uncertainty)) ;
l'axe d'évolution mesure l'ubiquité et la certitude, pas le temps
([blog Bits or pieces](https://blog.gardeviance.org/2015/02/an-introduction-to-wardley-value-chain.html)).

**En quoi c'est semblable.** C'est presque terme à terme l'architecture de l'Alphabet : une
grammaire transversale, des composants qui se déplacent, des forces non choisies et des coups
contextuels. Les deux prétendent dire quelque chose qui ne dépende pas du domaine.

**L'écart décisif.** Wardley affirme **une loi de transition** ; l'Alphabet affirme l'inverse, en
toutes lettres — **P1** : « Une représentation commune ne démontre ni une loi de transition commune
ni une même temporalité. » La matrice de l'Alphabet est un ensemble d'arêtes stipulées, sans sens de
circulation obligé ; Wardley a une direction, une notion de maturité observable et une inertie liée
au succès passé. L'Alphabet a des dates, un horizon et un score ; Wardley n'en a pas.

**L'épreuve.** La question qui départage n'est pas « trouve-t-on des contre-exemples ? » — Wardley a
une réponse préparée : le composant ne recule pas, c'est un composant d'ordre supérieur qui naît.
La question est : **existe-t-il un critère décidable qui distingue « le même composant recule » de
« un autre composant naît » ?** Si le critère n'existe pas, la loi est protégée de la réfutation par
renommage, et P1 est mieux fondée. Si le critère existe, Wardley devient le concurrent le plus
sérieux du corpus et P1 doit être réécrite.

**Ce qu'il faut lui emprunter.** La maturité comme observable — l'ubiquité, la standardisation,
l'existence d'un marché — et l'inertie liée au succès passé, plus fine que « l'état dépend du
chemin ».

**Ce qui est refusé.** Les quarante principes de doctrine comme prescriptions universelles, et la
carte comme artefact de facilitation : l'Alphabet ne prescrit pas d'action.

---

### 3.2 Cynefin — le rival qui nie la possibilité de prévoir

**L'appareil.** Cinq domaines — *clear*, *complicated*, *complex*, *chaotic*, et le cinquième,
longtemps appelé *confused* ou *disorder*, désormais **aporetic** dans la présentation de 2026
([The Cynefin Co, 9 février 2026](https://thecynefin.co/category/cynefin/)). À chaque domaine sa
manière de décider : *sense–categorise–respond*, *sense–analyse–respond*,
**probe–sense–respond**, *act–sense–respond*. À chaque domaine son type de contrainte : rigide,
gouvernante, **habilitante**, absente. Cynefin se présente comme un cadre de décision, pas comme un
modèle : « it has not been conceived to describe or to predict the structure or functioning of
anything » ([cynefin.io](https://cynefin.io/index.php/Cynefin)).

**La thèse.** Dans le complexe, les causalités ne sont cohérentes qu'avec le recul ; on ne peut pas
prédire, on sonde. La prescription est explicite : des portefeuilles de sondes *safe-to-fail*, en
parallèle, avec des stratégies d'amplification et d'amortissement définies à l'avance.

**En quoi c'est semblable.** La carte CONTRAINTE de l'Alphabet et la typologie de Cynefin décrivent
le même observable : une règle qui retire des options. Cynefin en distingue quatre types, dont un —
la contrainte **habilitante** — que l'Alphabet n'a pas : une contrainte qui **ouvre** des possibles
en contraignant.

**L'écart décisif.** Les deux affirmations ne peuvent pas être vraies ensemble dans le même domaine.
Si Cynefin a raison, le mode PRÉVOIR de l'Alphabet est invalide là où il prétend servir. Si
l'Alphabet a raison, la thèse centrale de Cynefin est fausse. Il n'y a pas de compromis
« les deux sont utiles selon les cas » : il faut dire **dans quel domaine** une lecture par alphabet
opère. La réponse que l'Alphabet peut soutenir est étroite : il ne prédit pas le système, il prédit
la **transition d'une structure** conditionnellement à la répétition d'un motif observé, avec un
barreau A et un score. Ce n'est pas la même prétention.

**L'épreuve.** C'est le test le moins cher du corpus. Prendre N situations déjà lues par l'Alphabet ;
deux lecteurs compétents, à l'aveugle, attribuent (a) un domaine Cynefin, (b) un jeu de cartes.
Mesurer κ, PABAK et les deux taux de manque avec `moteur.py accord`. Si κ(Cynefin) ≈ 0 et
κ(Alphabet) > 0, Cynefin ne peut pas être un instrument de lecture concurrent. Si les deux sont
proches de 0, le problème est l'instrument, pas le rival. Si κ(Cynefin) > κ(Alphabet), la typologie
des contraintes est un meilleur vocabulaire pour ce matériau.

**Ce qu'il faut lui emprunter.** La contrainte habilitante, et la distinction entre quatre types de
contraintes plutôt qu'un seul.

**Ce qui est refusé.** La prescription (« probe–sense–respond »), le vocabulaire de management
(*safe-to-fail*, amplification, amortissement), et l'idée que Cynefin serait un modèle prédictif.

---

### 3.3 MACTOR — le rival qui modélise les acteurs

**L'appareil.** Développée en 1989-1990 par François Bourse et Michel Godet, MACTOR
(Méthode ACTeurs, Objectifs, Rapports de force) décrit un système par une matrice acteurs ×
objectifs. Sept phases : tableau des stratégies, enjeux et objectifs, positionnement, hiérarchisation
des priorités, matrice d'influences directes et indirectes (0 à 4), intégration des rapports de force,
recommandations et questions clés
([mactorprospective.com](https://www.mactorprospective.com/) ; Godet, *Futures*, 1991,
[doi:10.1016/0016-3287(91)90082-D](https://doi.org/10.1016/0016-3287(91)90082-d)).

**En quoi c'est semblable.** Le modèle d'acteurs est le même objet que la carte INCERTITUDE de
l'Alphabet, dont la définition commence par « pour les acteurs de la situation, plusieurs états
futurs ou cachés restent possibles, et cette indétermination organise leurs conduites ». MACTOR
formalise ce que l'Alphabet se contente de nommer : qui peut bloquer, qui peut imposer, quelles
alliances sont plausibles.

**L'écart décisif.** MACTOR produit une **aide à la décision** pour un acteur, avec des
recommandations stratégiques ; l'Alphabet ne prescrit pas d'action et ne nomme pas les acteurs. MACTOR
travaille sur 10 à 20 acteurs et des objectifs explicites ; l'Alphabet travaille sur des structures
et des strates. MACTOR ne produit pas de probabilité ; l'Alphabet en produit une, avec un intervalle
et un niveau de provenance.

**L'épreuve.** Sur un même dossier, comparer les questions que chaque méthode fait apparaître :
MACTOR devrait nommer des acteurs et des objectifs que l'Alphabet laisse implicites ; l'Alphabet
devrait nommer des structures que MACTOR ne voit pas. Le test n'est pas de savoir laquelle « a
raison », mais laquelle produit une **liste de questions discriminantes** plus courte et plus utile.

**Ce qu'il faut lui emprunter.** La matrice d'influences et le calcul des rapports de force, comme
complément à INCERTITUDE — sans changer le calcul de `p`.

---

### 3.4 ACH — le rival de la discipline de preuve

**L'appareil.** L'*Analysis of Competing Hypotheses* de Heuer, diffusée par le *Tradecraft Primer*
de la CIA : lister toutes les hypothèses raisonnables, construire une matrice hypothèses × preuves,
marquer chaque preuve comme cohérente, incohérente ou neutre, puis chercher à **réfuter** les
hypothèses plutôt qu'à confirmer la préférée. Le *primer* insiste sur la valeur diagnostique d'une
preuve — celle qui ne soutient qu'une hypothèse — et sur la sensibilité aux quelques items critiques
([CIA, *A Tradecraft Primer*, 2009](https://www.cia.gov/resources/csi/static/Tradecraft-Primer-apr09.pdf)).

**En quoi c'est semblable.** C'est la même éthique que A1–A8 : nommer les alternatives, chercher la
contradiction, documenter ce qui départage. L'Alphabet ajoute une probabilité et une classe de
référence ; ACH ajoute une matrice de preuves et une trace de raisonnement.

**L'écart décisif.** ACH ne produit pas de probabilité, ne définit pas de classe de référence et ne
score pas ses jugements. L'Alphabet produit un chiffre, mais ne construit pas de matrice
hypothèses × preuves : ses « questions qui départagent » en sont une version pauvre. ACH est
meilleur pour **tracer** un raisonnement ; l'Alphabet est meilleur pour **mesurer** une répétition.

**L'épreuve.** Prendre dix dossiers de l'Alphabet, demander à un analyste ACH de classer les
hypothèses, puis comparer l'ordre obtenu au `p` de l'Alphabet. Si l'ordre ACH et l'ordre `p`
divergent, l'un des deux instruments mesure autre chose que ce qu'il prétend.

**Ce qu'il faut lui emprunter.** La matrice hypothèses × preuves, et le critère de valeur
diagnostique, comme pièce du dossier de lecture.

---

### 3.5 Analyse morphologique — le rival de l'exhaustivité

**L'appareil.** La *General Morphological Analysis* de Zwicky : définir les paramètres du problème,
leur donner des valeurs, construire un « champ morphologique » de toutes les configurations, puis
éliminer par **évaluation de cohérence croisée** les combinaisons incompatibles. Une réduction de
90 à 99 % de l'espace est courante ; la méthode est non quantifiée et non causale
([Ritchey, *General Morphological Analysis*](https://www.swemorph.com/ma.html) ;
[Ritchey, *Technological Forecasting and Social Change*, 2018](https://doi.org/10.1016/j.techfore.2017.05.027)).

**En quoi c'est semblable.** L'Alphabet est, lui aussi, un espace de configurations : 16 cartes ×
13 strates, avec des incompatibilités (G6) qui retirent des états. La différence est que l'Alphabet
affecte une probabilité aux configurations et les révise par les cas.

**L'écart décisif.** GMA ne dit rien de la fréquence des configurations ; elle dit ce qui est
**possible** et **cohérent**. L'Alphabet dit ce qui est **probable** et **révisable**. GMA est
meilleure pour ne rien oublier ; l'Alphabet est meilleur pour trancher entre deux avenirs.

**L'épreuve.** Comparer, sur un même dossier, le nombre de configurations cohérentes produites par
GMA et le nombre d'états que l'Alphabet peut écrire. Si GMA produit beaucoup plus d'états
intéressants que l'Alphabet, le vocabulaire de l'Alphabet est trop pauvre ; si elle en produit
surtout d'incompatibles, l'Alphabet a déjà fait le travail.

**Ce qu'il faut lui emprunter.** L'évaluation de cohérence croisée comme contrôle de complétude du
vocabulaire, et la distinction entre « impossible », « improbable » et « non modélisé ».

---

### 3.6 Scénarios — le rival de l'horizon

**L'appareil.** La planification par scénarios de Shell et du Global Business Network : identifier
la question focale, les forces motrices, les **éléments prédéterminés** et les **incertitudes
critiques**, puis construire deux à quatre récits cohérents — souvent une matrice 2 × 2 — pour
éprouver une décision. Les scénarios ne sont pas des prévisions : ce sont des hypothèses de futurs
destinés à révéler des risques
([Wack, *Harvard Business Review*, 1985](https://fenix.iseg.ulisboa.pt/downloadFile/1126033050846405/Wack%20HBR%20Uncharted%20Waters%20Ahead%201985.pdf) ;
[GBN, *Plotting Your Scenarios*](https://adaptknowledge.com/wp-content/uploads/rapidintake/PI_CL/media/gbn_Plotting_Scenarios.pdf)).

**En quoi c'est semblable.** Même souci de ne pas confondre prévision et exploration, même usage de
l'incertitude comme structure, même refus de la précision fausse. L'Alphabet partage avec les
scénarios l'idée que l'avenir n'est pas une trajectoire unique.

**L'écart décisif.** Les scénarios ne produisent pas de probabilité et ne se scorent pas. L'Alphabet
produit un chiffre, un intervalle et un score. Les scénarios sont meilleurs pour **préparer une
décision** ; l'Alphabet est meilleur pour **mesurer une répétition**.

**L'épreuve.** Sur les mêmes dossiers, comparer le nombre de décisions que chaque méthode ferait
changer. Si les scénarios font changer plus de décisions à coût égal, l'Alphabet doit justifier son
chiffre ; si l'Alphabet fait changer plus de décisions, les scénarios doivent justifier leur récit.

**Ce qu'il faut lui emprunter.** La distinction entre éléments prédéterminés et incertitudes
critiques, et l'usage de l'horizon comme variable de conception, pas comme paramètre caché.

---

### 3.7 Bueno de Mesquita — le rival quantifié, et sa réplication de 2026

**L'appareil.** Un modèle de négociation entre acteurs, résolu en équilibres bayésiens parfaits.
Entrées : les acteurs, leur position, leur **saillance**, leur **capacité de persuasion**, leur
**flexibilité**. Sortie : l'issue attendue, avec intervalle. Les entrées viennent d'entretiens
experts : « experts are not asked how they think the issue will be resolved ». Le code commercial
n'est pas public ; Bueno de Mesquita lui-même indique que les droits commerciaux appartiennent à un
tiers ([Theory Talks #31](https://theory-talks.com/talks/31-bruce-bueno-de-mesquita)).

**Les chiffres revendiqués.** Stanley Feder, ancien analyste de la CIA, rapporte que le modèle
était « on target » dans 90 % des cas et « bull's eye » dans 60 %, contre 30 % pour les experts —
qui fournissaient les entrées. Une étude sur 21 décisions communautaires européennes donne 97 %
([Hoover Institution](https://www.hoover.org/research/it-all-adds)). Ces chiffres viennent de
l'auteur et de ses défenseurs ; Green (2002) soutient qu'ils sont cités de façon sélective.

**La critique décisive.** Scholz, Calbert et Smith (*Journal of Theoretical Politics* 23(4), 2011,
p. 510-531) montrent qu'« aucune élucidation claire du modèle n'existe dans la littérature ouverte » ;
ils doivent le reconstituer pièce par pièce et relèvent des problèmes de sensibilité et de
convergence ([doi:10.1177/0951629811418142](https://doi.org/10.1177/0951629811418142)). Un modèle
qu'on ne peut pas reconstituer n'est pas un étalon.

**La réplication de 2026.** Une réplication ouverte et pré-enregistrée évalue le modèle sur 351
controverses législatives européennes contre un benchmark plus simple : la moyenne des positions des
acteurs pondérée par capacité et saillance. Le modèle échoue au seuil de précision pré-enregistré, et
aucun des huit concepts de solution testés ne se sépare de la moyenne sur données tenues à l'écart.
Conclusion de l'auteur : les succès documentés viennent de l'**élicitation structurée**, pas de la
dynamique de solution — « structure, not magic »
([Hassan, SSRN, août 2026](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7285840)). C'est un
preprint, pas une publication évaluée par les pairs ; il converge néanmoins avec la critique de
Scholz et al. et avec le résultat de Green & Armstrong sur la pluralité forcée.

**L'écart décisif.** L'Alphabet ne nomme pas les acteurs et ne résout pas un jeu. Il parie sur une
transition de structure. Bueno de Mesquita parie sur une issue nominative. Les deux ne répondent pas
à la même question — et c'est précisément pourquoi l'Alphabet doit dire, plus clairement qu'il ne le
fait, que son refus des issues nominatives n'est pas un refus de la prévision.

**Ce qu'il faut lui emprunter.** L'élicitation structurée des entrées, et la discipline de publier
les prévisions avant l'issue. Ce que l'Alphabet fait déjà, mais sans acteurs.

---

### 3.8 Cliodynamique — le rival qui a déjà fait ce que l'Alphabet n'a pas fait

**L'appareil.** La théorie structure-démographique de Peter Turchin relie trois forces — l'appauvrissement
populaire, la compétition intra-élitaire et la faiblesse de l'État — à un **indicateur de stress politique**
qui, rétrospectivement, suit les vagues d'instabilité. Le modèle est quantifié, calibré sur des siècles, et
appliqué par pays.

**Le fait accompli.** En février 2010, Turchin publie dans *Nature* une courte correspondance :
« The next decade is likely to be a period of growing instability in the United States and western
Europe », avec un mécanisme et un pic attendu autour de 2020
([*Nature* 463, 608, 2010](https://doi.org/10.1038/463608a)). En 2020, il en publie lui-même
l'évaluation rétrospective : les manifestations antigouvernementales et les émeutes ont augmenté d'un
**ordre de grandeur** après 2010 aux États-Unis et au Royaume-Uni, sur des données allant jusqu'en
2018, ce qu'il lit comme une confirmation du modèle
([*PLOS ONE*, 2020](https://doi.org/10.1371/journal.pone.0237458)).

**En quoi c'est semblable.** Même ambition : une grammaire de forces transversales, un horizon, une
prédiction. Même refus de la description pure.

**L'écart décisif.** L'Alphabet est **épistémologiquement supérieur et empiriquement inférieur**.
Supérieur : modèle nul explicite, `p_sans_cartes`, placebo, ρ, refus de chiffrer l'inconnu, critère de
réfutation par question. Inférieur : Turchin a une prédiction **datée, publique, résolue**, et l'Alphabet a
zéro cas.

**Ce qu'il faut dire honnêtement de cette évaluation.** Elle est faite par les auteurs du modèle, pas par
une équipe indépendante ; elle porte sur des indicateurs choisis après coup, et sur une décennie entière
plutôt que sur une date. C'est une confirmation **faible** — mais c'est une confirmation, et l'Alphabet n'a
rien d'équivalent.

**Ce que l'Alphabet ne dit pas et devrait dire.** Il n'a pas besoin de battre la théorie
structure-démographique sur la portée. Il a besoin de faire ce qu'elle a fait : **une** prédiction datée,
publique, résolue. Il en a la machinerie, et de plus disciplinée.

---

### 3.9 Panarchie — le rival du bloc, et l'avantage que l'Alphabet n'énonce jamais

**L'appareil.** Le cycle adaptatif de Holling : quatre phases — exploitation (r), conservation (K),
libération (Ω), réorganisation (α) — dans un espace à trois dimensions (potentiel, connectivité,
résilience). Les cycles sont emboîtés à des échelles différentes : c'est la **panarchie**.

**En quoi c'est semblable.** Le cycle adaptatif est le concurrent direct de **CROISSANCE + TRANSFORMATION
+ SEUIL + TRACE·MÉMOIRE pris comme un bloc**. Même objet : la croissance, la conservation, la rupture, la
mémoire.

**L'écart décisif, et il est structurel.** Le champ se demande lui-même si le cycle est « plus qu'une
métaphore » — c'est le titre d'un article de *Ecological Complexity* (Sundstrom & Allen, 2019,
[doi:10.1016/j.ecocom.2019.100767](https://doi.org/10.1016/j.ecocom.2019.100767)), écrit par des auteurs
sympathiques au cadre. La faiblesse est connue : **le cycle échoue ou réussit en bloc**. On ne peut pas
falsifier une phase sans falsifier le cadre.

**L'avantage que l'Alphabet possède et n'énonçait pas.** La **décomposabilité**. RÉSONANCE@7 peut être
*Vide* — trois recherches, close, « non concluant » — sans que les quinze autres cartes soient affectées.
Panarchy ne peut pas se permettre une phase vide. C'est une supériorité réelle, vérifiable dans le paquet,
et elle est désormais écrite (§16.4 des apports théoriques depuis 0.7.12), après avoir été relevée par
l'audit V34.

---

### 3.10 Théorie des catastrophes — l'ancêtre direct de SEUIL, et le correctif que l'Alphabet a trouvé

**L'appareil.** La théorie des catastrophes de René Thom modélise les discontinuités par la géométrie des
singularités : sept catastrophes élémentaires, dont la **fronce** (*cusp*) — hystérésis, bistabilité, aller
et retour basculant à des valeurs différentes du paramètre de contrôle. Zeeman l'a appliquée aux sciences
sociales, notamment dans un modèle de guerre avec Isnard
([Isnard & Zeeman, 1976](https://www.taylorfrancis.com/chapters/edit/10.4324/9780429267055-3/models-catastrophe-theory-social-sciences-isnard-zeeman)).

**En quoi c'est semblable.** **SEUIL *est* la fronce.** Même ADN mathématique : hystérésis, deux états
stables, un retour qui ne reprend pas le même chemin. C'est le concurrent le plus littéral du corpus.

**L'échec, et sa cause exacte.** Le programme a été abandonné en sciences sociales pour une raison
précise : les paramètres de contrôle n'étaient pas mesurés indépendamment, si bien que le modèle
s'ajustait après coup à n'importe quelle discontinuité. La critique de Sussmann et Zahler est restée
célèbre : « les catastrophes censées rendre compte du comportement réel ne sont qu'une reformulation du
fait que des discontinuités existent ; aucun résultat mathématique profond n'est réellement utilisé »
([*Synthese* 37, 117-216, 1978](https://doi.org/10.1007/BF00869575) ;
[critique du modèle d'Isnard-Zeeman](https://doi.org/10.1002/bs.3830230409)).

**Ce que l'Alphabet fait de mieux sans le dire assez.** Il exige un **marqueur local** — « franchissement
d'un seuil *reconnu par les parties* : emploi d'une arme interdite, frappe sur le territoire, attaque
délibérée de civils » — c'est-à-dire une mesure **indépendante du modèle**. C'est exactement le correctif
que la théorie des catastrophes n'a pas su trouver. L'Alphabet a résolu le problème qui a tué son ancêtre ;
il le mentionne depuis 0.7.12, et c'est l'un de ses trois arguments les plus forts.

---

### 3.11 *Dynamics of Contention* — le trou le plus surprenant

**L'appareil.** McAdam, Tarrow et Tilly (2001) identifient des **mécanismes causaux récurrents** —
courtage (*brokerage*), formation de catégories (*category formation*), défection des élites
(*elite defection*), appropriation sociale, attribution de menace et d'opportunité, diffusion — et des
**processus** qui les combinent, pour comparer dix-huit épisodes de contestation depuis la Révolution
française. Le projet est explicitement de traverser les domaines : grèves, guerres, révolutions,
mouvements sociaux.

**En quoi c'est semblable.** C'est, en ambition, **le concurrent le plus proche** : un alphabet de
mécanismes transposables, avec une communauté empirique derrière et des épisodes comparés. Là où Wardley
vient de la stratégie d'entreprise et Cynefin du management, DoC vient exactement du terrain de la strate 7.

**L'écart décisif.** DoC ne produit ni probabilité, ni score, ni classe de référence ; il produit une
**narration causale comparable**. L'Alphabet produit un chiffre et une trace, mais ne sait pas nommer les
mécanismes qui relient deux cartes.

**Pourquoi c'est une opportunité et pas une menace.** Une table de correspondance 16 cartes ↔ ~20
mécanismes produirait l'un de deux résultats, tous deux utiles : soit l'Alphabet est une **redescription**
de DoC — et il faut le savoir —, soit il ajoute la **dimension de strate**, et c'est un résultat
publiable. Le dépôt a inscrit cette table en attente (§16.3 des apports théoriques) : « une heure de
lecture, texte en main ». C'est le meilleur rapport effet/coût de tout le corpus concurrentiel, et il n'a
pas été fait.

---

## 4. Les concurrents de la chaîne de prévision

### 4.1 CAMEO, GDELT, POLECAT — l'échelle contre la profondeur

CAMEO code des actes : verbe, acteur, cible. GDELT en produit des millions, avec un rappel très
élevé et une précision de domaine plus faible. **POLECAT** est le successeur d'ICEWS : codeur
machine fondé sur l'ontologie PLOVER, sept langues, plus de mille sources, mises à jour horaires,
événements de 2018 à aujourd'hui
([Dataverse](https://doi.org/10.7910/dvn/lmfpip)). Une comparaison de juin 2026 conclut que GDELT
convient à l'alerte macro à haut rappel, POLECAT aux signaux à haut rapport signal/bruit
([*Data*, 2026](https://doi.org/10.3390/data11070158)).

**Le rapport à l'Alphabet.** Même chaîne — texte → code → état → pari —, autre unité : l'acte au lieu
de la structure. L'Alphabet perd l'échelle et la reproductibilité automatique ; il gagne la
profondeur et l'interprétabilité. Le flux d'événements peut servir de **faits datés** pour la strate
7, pas de modèle.

### 4.2 ViEWS — le concurrent opérationnel

ViEWS produit des prévisions mensuelles de conflit armé, au niveau pays-mois et sur une grille de
0,5°, à 1–36 mois. Le modèle `fatalities003` est en service depuis novembre 2025 ; les prévisions
d'octobre 2026 couvrent septembre 2026 à août 2029
([viewsforecasting.org](https://viewsforecasting.org/)). C'est un système mature, ouvert, évalué en
continu, mono-domaine.

**Le rapport à l'Alphabet.** ViEWS est ce que l'Alphabet n'est pas : un système quantitatif
opérationnel, avec des données massives et une maintenance. L'Alphabet est ce que ViEWS n'est pas :
un vocabulaire trans-domaines, lisible, avec une trace de lecture. Les deux ne se remplacent pas ;
ils se comparent sur la seule chose commune — la calibration probabiliste d'événements datés.

### 4.3 Superforecasters — le concurrent humain

Good Judgment publie un track record de 831 questions résolues au 6 août 2026 : 73 % de jours où la
probabilité la plus haute porte sur la bonne issue, 79 % de prévisions meilleures que les équipes
hybrides homme-machine. Les superforecasters ont battu Polymarket d'environ 18 à 24 % sur 25
réunions de banques centrales
([Good Judgment](https://goodjudgment.com/resources/the-superforecasters-track-record/) ;
[comparaison Polymarket](https://goodjudgment.com/testing-polymarkets-most-accurate-claim/)).

**Le rapport à l'Alphabet.** Les superforecasters sont le **meilleur comparateur humain** disponible.
Ils ne partagent pas l'ontologie de l'Alphabet, mais ils partagent son objet : une probabilité sur un
événement défini. Toute prévision de l'Alphabet qui ne les bat pas n'est pas un résultat.

### 4.4 Marchés de prédiction — le concurrent liquide

Metaculus, Polymarket, Manifold : des prix ou des agrégats qui reflètent l'information disponible.
Metaculus revendique 3,2 millions de prédictions et 22 000 questions sur douze ans
([Metaculus](https://www.metaculus.com/futureeval/)). Les marchés sont un benchmark de liquidité,
pas de méthode : ils disent ce que le marché sait, pas pourquoi.

### 4.5 Prévisionnistes LLM — le concurrent de 2026

Trois dispositifs font référence :

- **ForecastBench** : benchmark dynamique de 1 000 questions, sans contamination ; les experts
  battent le meilleur LLM (p < 0,001), et les LLM dépassent le public mais restent derrière les
  superforecasters
  ([ForecastBench](https://www.forecastbench.org/) ;
  [papier 2026](https://faculty.wharton.upenn.edu/wp-content/uploads/2026/02/ForecastBench_A_Dynamic_.pdf)).
- **FutureEval / Metaculus** : au printemps 2026, l'équipe de bots la plus forte est à −1,25 point
  en tête-à-tête avec les Pros, contre −20,03 au deuxième trimestre 2025 ; l'écart n'est plus
  statistiquement significatif (p = 0,247)
  ([Metaculus, analyse du printemps 2026](https://www.metaculus.com/notebooks/45373/spring-2026-futureeval-analysis/)).
- **Prophet Arena** : benchmark vivant, décomposition du pipeline ; les LLM montrent une bonne
  calibration mais des faiblesses de rappel d'événements et de compréhension des sources
  ([ICLR 2026](https://iclr.cc/virtual/2026/poster/10009102)).

**Le rapport à l'Alphabet.** C'est le concurrent le plus rapide et le plus financé. Il n'a pas
d'ontologie fixe : il synthétise le corpus. L'Alphabet a une ontologie et une trace ; il n'a pas
d'échelle. Le test décisif n'est pas « l'LLM est-il meilleur ? » mais « l'ontologie ajoute-t-elle
quelque chose à un LLM qui lit le même dossier ? ». C'est exactement le **bras externe** que le
dépôt a ajouté en 0.7.8 (`sceller-comparateur`).

### 4.6 Quelle barre ? Le chiffre contesté, et ce qu'il vaut vraiment

Le dépôt cite parfois « les meilleurs modèles au niveau des superprévisionnistes en 2026 ». Un audit
de la 0.7.11 a objecté que la barre est peut-être **trop haute**, en s'appuyant sur une évaluation de
2025 : o3 à **0,1352** de Brier médian contre **0,0225** pour un groupe d'experts. Le dépôt a
explicitement refusé de reprendre ces valeurs, faute de vérification (§16.2 des apports théoriques).

Elles sont vérifiables, et la vérification change la lecture. Dans l'article original
(Lu, 2025, [arXiv:2507.04562](https://arxiv.org/abs/2507.04562)) :

| Groupe | Brier **médian** | Brier **moyen** | n |
|---|---|---|---|
| o3 (raisonnement, 5 tirages) | 0,1352 | 0,1362 | 464 |
| Experts (Metaculus) | **0,0225** | **0,1573** | 157 |

Le 0,0225 n'est donc pas « les experts sont six fois meilleurs ». C'est une **médiane très basse sur une
distribution très asymétrique** : beaucoup de prévisions expertes quasi parfaites sur des questions
tranchées, et une queue qui remonte. En **moyenne**, les experts (0,1573) sont *derrière* o3 (0,1362).
Les deux chiffres disent donc des choses différentes, et le seul honnête est : « sur ce jeu de questions,
les experts ont une médiane bien meilleure et une moyenne légèrement pire ; l'échantillon expert est
petit (157 questions, 41 en réserve) et l'intervalle est large ».

**Conséquence pour la barre de comparaison.** Elle est **plus basse** que « superprévisionniste » — un
modèle seul est autour de 0,13 — mais elle n'est pas basse du tout : c'est le niveau d'un très bon
prévisionniste amateur, pas d'un hasard. Un alphabet qui ne battrait pas 0,13 sur des questions
comparables n'aurait rien démontré. Et « battre un modèle seul » n'est pas la bonne cible : la cible est
le **même modèle avec le même dossier**, ce que `sceller-comparateur` permet déjà.

En 2026, la situation a encore bougé : au printemps, l'équipe des meilleurs bots est à −1,25 point en
tête-à-tête avec les Pros, écart non significatif (p = 0,247). Autrement dit, le concurrent n'est plus
« un modèle seul à 0,13 » mais « un système agentique plus recherche et agrégation, au niveau des
professionnels ». C'est contre celui-là qu'il faudra se mesurer, et c'est plus dur que ce que l'audit
de la 0.7.11 supposait.

---

## 5. Les cadres de calcul ne sont pas des rivaux

PyCIB (Cross-Impact Balance), FCMpy (cartes cognitives floues), pgmpy (réseaux bayésiens), EMA
Workbench (exploration sous incertitude profonde) et `forecasting-tools` de Metaculus sont des
**cadres de calcul**. Ils ne prétendent pas dire quelle est la bonne ontologie ; ils calculent les
conséquences de celle qu'on leur donne.

| Cadre | Ce qu'il calcule | Ce qu'il ne dit pas | Ce que l'Alphabet peut lui emprunter |
|---|---|---|---|
| **PyCIB** | scénarios cohérents, succession, Monte Carlo, robustesse | si le modèle est vrai | la cohérence croisée et l'exploration de scenarios |
| **CIB** (Weimer-Jehle) | une **consistance de configuration** à partir d'impacts entre descripteurs | si les descripteurs sont les bons | l'incompatibilité G6 et `antagonismes.md` suffisent déjà à calculer une consistance : le calcul n'est pas fait |
| **FCMpy** | poids causaux flous, simulation, intervention | si les nœuds sont les bons | l'élicitation qualitative et les what-if |
| **pgmpy** | inférence, découverte causale, intervention | si la structure est identifiée | la distinction entre observation et intervention |
| **EMA Workbench** | exploration d'ensembles de modèles sous incertitude profonde | quelle politique est juste | l'exploration systématique des variantes |
| **`forecasting-tools`** | agrégation, calibration, score | ce qui mérite d'être prévu | la discipline de scoring |
| **QCA** (Ragin) | **consistance** et **couverture** d'une règle configuration → issue | si la configuration est causale | la mesure qui manque à `confronter` |

Le dépôt l'a déjà noté : ces cadres ne sont pas des concurrents au même titre que Wardley ou
Cynefin. Leur apport est de rendre les hypothèses et leurs conséquences explicites. Le risque, en
les prenant pour des rivaux, est de croire qu'un meilleur solveur corrige une mauvaise ontologie.

### 5.1 Deux déficits instrumentaux précis

**QCA — consistance et couverture.** Ragin pose une question que l'Alphabet ne sait pas poser : quelle
est la **consistance** de la règle « cette configuration → cette issue », et quelle est sa **couverture** ?
Les paramètres d'ajustement sont standardisés (consistance = Σ min(Xᵢ,Yᵢ) / Σ Xᵢ ; couverture = mesure de
la pertinence empirique d'un sous-ensemble consistant,
[Ragin, *Political Analysis* 14(3), 2006](https://doi.org/10.1017/S1047198700002195) ;
[notes de Ragin](https://compasss.org/wp-content/uploads/2024/11/Research-Notes-1.pdf)).

L'Alphabet a exactement les ingrédients : des configurations (les états), une issue (l'événement), et des
cas. Il n'a aucun équivalent de ces deux nombres. `confronter` compte les occasions d'éprouver une arête,
ce qui est proche, mais ne mesure ni la consistance d'une règle ni sa couverture. C'est le déficit
instrumental le plus net, et il rendrait l'artefact lisible par une communauté entière.

**Gentner — la similarité relationnelle.** L'homologie H1.5 est un **Jaccard pondéré sur des ensembles de
cartes** : une similarité d'**attributs**. La théorie du *structure-mapping* dit qu'une analogie valable
est une similarité de **relations** et de leur systématicité, pas d'attributs. Le dépôt revendique
« l'analogie structurale » et mesure la version la plus faible. L'écart entre le mot et la mesure est
inscrit en attente (§16.3) : les liaisons G3 n'entrent pas dans l'homologie. C'est un écart de
vocabulaire, pas de calcul — mais il porte sur le mot central du dépôt.

**Inférence séquentielle — résolu, et c'est le point à ne pas manquer.** L'audit de la 0.7.11 avait
identifié un défaut réel : les tests exacts du signe et de Wilcoxon sont à **effectif fixe**, or le
journal est **croissant** ; les lire à 50, 80 puis 120 épisodes et s'arrêter au premier franchissement
gonfle l'erreur de type I. Les suites de confiance de Howard, Ramdas, McAuliffe et Sekhon
([*Annals of Statistics* 49(2), 2021](https://doi.org/10.1214/20-AOS1991)) sont valides à tout instant,
sous tout arrêt facultatif, sans hypothèse asymptotique ; et la comparaison séquentielle de deux
prévisionnistes a sa propre procédure
([*Operations Research*, 2021](https://doi.org/10.1287/opre.2021.0792)).

Le dépôt a intégré ce correctif en 0.7.12 (`e_processus` dans chaque différentiel, `v4.sequentiel` à côté
du statut). C'est l'exemple le plus net d'un audit qui a produit une correction réelle, et il faut le
créditer : peu de projets de cette taille corrigent un défaut de test en une version.

---

## 6. Ce que l'Alphabet fait que les autres ne font pas — et l'inverse

### 6.1 Ce qu'il fait seul, ou presque

| Capacité | Qui d'autre ? | Ce que cela vaut |
|---|---|---|
| **Ontologie finie et statuée** : 16 cartes × 13 strates, 208 cases, statuts Attesté/Documenté/Proposé/Vide/Hors domaine | GMA a un espace de configurations, pas des statuts de preuve ; CAMEO a un codebook, pas des strates | on peut voir ce qui est vérifié et ce qui ne l'est pas |
| **Classe de référence construite** + **placebo d'homologie** | aucun des dix travaux cités ne peut faire de placebo, faute d'« autres cas » | transforme une faiblesse structurelle en instrument |
| **Décomposition du chiffre** : a priori, cartes, homologie, niveau, horizon, variantes de codage | les cadres de calcul décomposent un modèle, pas une lecture | un résultat nul devient interprétable |
| **Protocole falsifiable** : dossier scellé, jugement scellé, pré-enregistrement, Brier, V4 | les superforecasters ont le score, pas le dossier scellé ; les marchés ont le prix, pas la trace | rend la prévision opposable |
| **« Non estimé »** au lieu d'un chiffre de remplacement | rare dans les outils opérationnels | refuse la fausse précision |

### 6.2 Ce que les autres font mieux

| Faiblesse de l'Alphabet | Qui fait mieux | Conséquence |
|---|---|---|
| **0 cas actif, 0 Attesté** | ViEWS, les superforecasters, les marchés, les LLM : tous ont des prévisions résolues | aucune performance hors échantillon ; le dépôt ne peut pas revendiquer de calibration |
| **1 codeur, κ non mesuré** | ACH et les méthodes d'analyse structurée ont des protocoles d'accord ; Cynefin a des critiques d'accord | la reproductibilité de la lecture n'est pas établie |
| **Pas de modèle d'acteurs** | MACTOR, Bueno de Mesquita | les issues nominatives sont abandonnées, pas résolues |
| **Pas de loi de direction** | Wardley | pas de réponse à « vers quoi cela va », seulement « quelle transition est probable » |
| **Pas de prescription** | Cynefin, MACTOR, scénarios | l'outil lit, il ne conseille pas — c'est un choix, mais un concurrent peut le reprocher |
| **Pas d'échelle** | GDELT, POLECAT, ViEWS | quelques faits lus et cités, pas des millions d'événements |
| **Pas de système publié de bout en bout** | les bots de FutureEval et de ForecastBench sont des systèmes complets, avec pipeline, recherche et agrégation | la comparabilité avec les bots est encore à construire |

### 6.3 Trois supériorités que le dépôt n'énonçait pas

L'audit de la 0.7.11 a relevé un défaut d'un autre ordre que les huit autres : un **excès de prudence**
qui empêche l'artefact de revendiquer ce qu'il fait mieux. Trois supériorités, vérifiables dans le paquet,
n'étaient écrites nulle part :

| Supériorité | Contre qui | Pourquoi elle est réelle |
|---|---|---|
| **Décomposabilité** | Panarchie (Holling) | une carte peut être *Vide* ou close dans une strate sans que les quinze autres soient touchées ; un cycle adaptatif échoue ou réussit en bloc |
| **Marqueur indépendant du modèle** | Théorie des catastrophes (Thom, Zeeman) | SEUIL a la même forme que la fronce, mais un fait ne l'ancre que par un marqueur local mesuré hors du modèle — ce qui empêche l'ajustement après coup à toute discontinuité |
| **Provenance ρ** | Tetlock, QCA, ViEWS | une échelle qui dit **d'où vient** le chiffre, distincte de sa fiabilité ; aucun des trois ne l'a |

Ces trois points sont désormais écrits dans le dépôt (§16.4 des apports théoriques, depuis 0.7.12). Il
faut le créditer : l'audit a produit un ajout, pas seulement une critique. Et il faut noter ce qu'ils ont
en commun — aucun n'est un compromis. Ils sont **structurels**, et ils resteraient vrais même si
l'Alphabet ne prédisait jamais rien de juste. C'est ce qui les rend solides, et c'est aussi ce qui les
rend insuffisants : un instrument peut être décomposable, bien ancré et bien tracé, et ne rien valoir comme
prévision.

### 6.4 Ce que l'audit de la 0.7.11 a établi, et ce que le dépôt en a fait

Le dépôt a consigné l'audit au §16 des apports théoriques et en a trié chaque point. Le tableau suivant
permet de savoir, en une page, ce qui est fermé et ce qui reste — et de ne pas imputer au dépôt un manque
qu'il a comblé.

| Point de l'audit | Ce que le dépôt a fait | Version |
|---|---|---|
| D3 · érosion de P1 par accommodation (6 cartes sur 13 modifiées en strate 7) | **compté**, règle proposée (≥ 2 marqueurs retirés dans ≥ 2 strates), **non appliquée** : la règle ne peut pas mordre avec une seule strate documentée | 0.7.12 |
| D4 · test exact à effectif fixe sur un journal croissant | **corrigé** : `e_processus` valide à tout instant dans chaque différentiel, `v4.sequentiel` à côté du statut | 0.7.12 |
| D5 · le placebo ne commande rien | **retenu comme drapeau**, pas comme condition de ρ : `homologie_discernable = false` quand p est dans la plage à 90 % du placebo. Changer ρ resterait une décision d'auteur | 0.7.12 |
| D6 · la fenêtre, levier le plus fort, hors de l'intervalle | **corrigé** : `bande_horizon` publie p à 1, 3 et 6 fenêtres, avec et sans cartes | 0.7.12 |
| D7 · P8 dit « non estimable », le moteur s'en sert quand même | **corrigé** dans l'ordre de lecture : `resultat_principal` imprime la paire (sans cartes, avec cartes) avant le reste, tant qu'aucun cas réel n'est actif | 0.7.12 |
| D1 · dériver ou calibrer λ | **non fait** : item 1.0 de la feuille de route, conditionné à un rédacteur indépendant de la matrice, sans responsable ni échéance | — |
| D2 · statut d'arête « Éprouvée » indexé sur l'arête, non sur la case | **non fait** : `confronter` calcule déjà les occasions ; le nom et l'effet sur ρ manquent | — |
| DoC · table 16 cartes ↔ mécanismes | **non fait** : inscrit en attente, « une heure de lecture, texte en main » | — |
| QCA · consistance et couverture | **non fait** : inscrit en attente, conditionné à des cas réels | — |
| Gentner · similarité relationnelle | **non fait** : l'écart entre « analogie structurale » et Jaccard d'attributs reste à écrire | — |
| L1 · test à trois bras | **inscrit** dans la feuille de route comme test à l'aveugle « proposé, non commencé » | 0.7.12 |

Sur onze points, **trois sont fermés** (D4, D6, D7), **trois retenus sous une forme partielle mais
honnête** (D3 compté sans règle appliquée ; D5 converti en drapeau plutôt qu'en condition de ρ ; L1
inscrit sans être commencé), et **cinq attendent** (D1, D2, DoC, QCA, Gentner). C'est un bon taux pour
un audit de cette sévérité — et il laisse intacte la conclusion de l'audit : *l'instrument est terminé,
la mesure n'a pas commencé*.

### 6.5 Le résultat qui compte

Aucun concurrent ne combine les cinq capacités de §6.1. Mais aucun concurrent ne commence avec
**zéro cas**. C'est la situation étrange de l'Alphabet : il a la méthode la plus explicite et la
preuve la plus faible. Le concours ne se joue donc pas sur « qui a la meilleure ontologie » — cela
ne se tranche pas sans données — mais sur **qui produit le premier résultat opposable**. Sur ce
terrain, ViEWS, les superforecasters et les bots ont une avance que le dépôt ne comble pas avec une
version de plus.

---

## 7. Le banc d'essai : huit protocoles

Les protocoles sont classés par coût. Aucun ne demande de changer une règle du dépôt ; tous
produisent un chiffre comparable.

| # | Objet | Protocole | Coût | Résultat qui compte |
|---|---|---|---|---|
| 1 | **Cynefin vs Alphabet** | 15 situations déjà lues, 2 lecteurs à l'aveugle, domaine Cynefin et jeu de cartes ; `moteur.py accord` | 2 × ½ journée | κ, PABAK, taux de manque comparés |
| 2 | **Wardley vs Alphabet** | lire le corpus Wardley en cherchant le critère d'identité d'un composant | 1 journée | critère décidable ou non ; si non, P1 est mieux fondée |
| 3 | **ACH vs Alphabet** | 10 dossiers, matrice hypothèses × preuves, ordre ACH contre ordre `p` | 1 journée | corrélation des ordres ; divergence localisée |
| 4 | **Bueno de Mesquita / jeu de rôle** | 10 questions nominatives déjà journalisées `origine: jugement` ; comparer jugement seul, simulation à 10 passes, modèle | 2–3 jours | le jugement seul est-il à ~32 % ? la simulation monte-t-elle vers 60 % ? |
| 5 | **Superforecaster / LLM** | sur les mêmes questions, `sceller-comparateur` avec un bras externe (humain ou bot), Brier et test du signe | 1–2 jours | l'Alphabet bat-il le meilleur comparateur ? |
| 6 | **ViEWS / GDELT** | sur la strate 7, mêmes événements datés, comparer la couverture et la calibration | 2–3 jours | l'ontologie ajoute-t-elle quelque chose au flux ? |
| **7** | **DoC vs Alphabet** | table de correspondance 16 cartes ↔ ~20 mécanismes de McAdam-Tarrow-Tilly, établie sur le texte, puis testée sur deux épisodes déjà codés | **1 heure** | redescription, ou apport de la strate — les deux résultats sont publiables |
| **8** | **QCA vs Alphabet** | sur 20 cas codés, calculer consistance et couverture de chaque règle « état → événement » | ½ journée | des nombres que l'Alphabet ne sait pas produire aujourd'hui |

Le protocole 1 est le moins cher et le seul qui mesure la **reproductibilité**, le terrain où
l'Alphabet est structurellement mieux placé que ses rivaux — sceau, empreinte, journal non réécrit,
κ publié — et qu'il n'a jamais revendiqué. Le protocole 5 est le seul qui mesure la **valeur
ajoutée** ; c'est celui que le dépôt a outillé en 0.7.8 sans encore le jouer. Et le protocole 7 est
le meilleur rapport effet/coût de tout ce document : une heure de lecture pour savoir si l'Alphabet
est une redescription de la sociologie relationnelle.

**Sur la mesure elle-même.** Le protocole 5, comme V4, compare des scores **épisode après épisode** sur
un journal croissant. Il faut donc une inférence valide à tout instant, pas un test à effectif fixe :
suites de confiance ou p-processus, comme le fait déjà `e_processus` depuis 0.7.12. Comparer deux
prévisionnistes séquentiellement a sa propre littérature
([*Operations Research*, 2021](https://doi.org/10.1287/opre.2021.0792)) ; s'en passer, c'est reproduire
le défaut que l'audit de la 0.7.11 avait trouvé.

---

## 8. Ce qu'il ne faut pas importer

- **La doctrine Wardley** (40 principes) : c'est une liste de prescriptions, exactement ce que
  `constitution.md` §5 refuse.
- **La prescription Cynefin** : *probe–sense–respond* est un conseil d'action, pas une structure
  observée.
- **Les recommandations stratégiques de MACTOR** : même refus.
- **Le modèle de Bueno de Mesquita comme étalon** : sa spécification n'est pas publique, et sa
  réplication ouverte de 2026 ne bat pas une moyenne pondérée.
- **Les chiffres de Feder** (90 %, 60 %, 97 %) comme acquis : ce sont des revendications de
  l'auteur et de ses défenseurs, pas des mesures indépendantes.
- **Le compromis « tout est complémentaire ».** Sur P1 (Wardley) et sur la possibilité de prévoir
  dans le complexe (Cynefin), il y a contradiction, pas complémentarité. Un dépôt qui se dit
  falsifiable doit le dire.
- **La théorie des catastrophes sans son correctif.** SEUIL peut emprunter sa forme à la fronce, mais
  pas sa méthode : sans marqueur local indépendant du modèle, le modèle s'ajuste après coup à toute
  discontinuité. C'est précisément ce que Sussmann et Zahler ont reproché à Isnard et Zeeman, et
  c'est ce que l'Alphabet a corrigé — il ne faut pas le défaire.
- **Le cycle adaptatif comme bloc.** Panarchy n'est pas importable carte par carte : ses phases
  n'ont pas d'existence séparée. Ce qui est importable, c'est la question de l'emboîtement d'échelles,
  pas la séquence r → K → α → Ω.
- **La cliodynamique comme preuve.** Sa prédiction de 2010 est réelle et datée ; son évaluation de
  2020 est faite par ses auteurs, sur des indicateurs choisis après coup. On peut envier son statut,
  pas reprendre ses conclusions.

---

## 9. Limites de ce document

- **Je n'ai pas lu les ouvrages primaires** de Wardley, Snowden, Godet, Heuer, Zwicky, Schwartz,
  Bueno de Mesquita, Turchin, Holling, Thom, Zeeman, McAdam, Tarrow, Tilly ou Ragin. J'ai lu des
  sources secondaires, des sites d'opérateurs, des articles évalués par les pairs et des chapitres
  d'ouvrage, listés en §10. Les appareils sont décrits de façon convergente par plusieurs sources ;
  les interprétations sont les miennes.
- **Les chiffres de performance ne sont pas comparables entre eux.** Ils portent sur des questions
  différentes, des horizons différents et des métriques différentes. Un Brier de 0,10 sur une
  question facile ne vaut pas un Brier de 0,10 sur une question difficile — et les auteurs de
  ForecastBench eux-mêmes notent que le score n'est pas comparable d'un jeu de questions à l'autre.
- **La réplication de 2026 de Bueno de Mesquita est un preprint.** Elle est cohérente avec la
  critique de 2011, mais elle n'a pas encore été évaluée par les pairs.
- **L'évaluation de la cliodynamique est autocritique.** Elle est produite par les auteurs du modèle
  et sur des indicateurs qu'ils choisissent. Elle établit qu'il y a eu une prédiction datée et une
  réévaluation — pas que le modèle est juste.
- **Je ne conclus pas que l'Alphabet est meilleur qu'un rival.** Aucun protocole de §7 ne mesure la
  justesse de l'Alphabet : il n'y a pas de cas actif. Le protocole 1 mesure un accord ; le 2 mesure
  la réfutabilité d'un rival ; le 5 mesure une valeur ajoutée ; le 7 mesure une redescription.
  Aucun ne dit que la lecture par cartes est juste.
- **Le corpus des concurrents bouge.** Cynefin a changé de cinquième domaine ; Wardley reste actif
  mais son site historique est en vente ; les bots de prévision progressent de plusieurs points par
  an. Ce document est daté du 31 octobre 2026.
- **Une source interne.** Les §3.9, §3.10, §6.3 et §6.4 s'appuient sur un audit du 31 octobre 2026
  visant la version 0.7.11. C'est un document de l'auteur du dépôt analysé, non une évaluation
  indépendante. Ses constats vérifiables ont été recoupés sur le paquet et sur les sources
  primaires ; ses jugements sont cités comme tels.

---

## 10. Sources

### Rivaux de même promesse

- Wardley, S. *Learn Wardley Mapping* — doctrine, climat, évolution :
  [learnwardleymapping.com](https://learnwardleymapping.com/doctrine/).
- Wardley, S. « You cannot measure evolution over time or adoption » :
  [wardleyleadershipstrategies.com](https://www.wardleyleadershipstrategies.com/climatic-patterns/you-cannot-measure-evolution-over-time-or-adoption-you-need-to-embrace-uncertainty).
- Wardley, S. « An introduction to Wardley (Value Chain) Mapping », *Bits or pieces?*, 2015 :
  [blog.gardeviance.org](https://blog.gardeviance.org/2015/02/an-introduction-to-wardley-value-chain.html).
- Snowden, D. « St David's 2026 », The Cynefin Co, 1er mars 2026 :
  [thecynefin.co](https://thecynefin.co/st-davids-2026-a-work-in-progress/).
- *Cynefin* — domaines, dynamiques, malentendus :
  [cynefin.io](https://cynefin.io/index.php/Cynefin).
- Godet, M. « Actors' moves and strategies: The MACTOR method », *Futures*, 1991 :
  [doi:10.1016/0016-3287(91)90082-D](https://doi.org/10.1016/0016-3287(91)90082-d).
- MACTOR — présentation et sept phases :
  [mactorprospective.com](https://www.mactorprospective.com/).
- Heuer, R. *A Tradecraft Primer: Structured Analytic Techniques for Improving Intelligence
  Analysis*, CIA, 2009 :
  [cia.gov](https://www.cia.gov/resources/csi/static/Tradecraft-Primer-apr09.pdf).
- Ritchey, T. *General Morphological Analysis* :
  [swemorph.com](https://www.swemorph.com/ma.html).
- Ritchey, T. « General morphological analysis as a basic scientific modelling method »,
  *Technological Forecasting and Social Change*, 2018 :
  [doi:10.1016/j.techfore.2017.05.027](https://doi.org/10.1016/j.techfore.2017.05.027).
- Wack, P. « Scenarios: Uncharted Waters Ahead », *Harvard Business Review*, 1985 :
  [PDF](https://fenix.iseg.ulisboa.pt/downloadFile/1126033050846405/Wack%20HBR%20Uncharted%20Waters%20Ahead%201985.pdf).
- Global Business Network. *Plotting Your Scenarios* :
  [PDF](https://adaptknowledge.com/wp-content/uploads/rapidintake/PI_CL/media/gbn_Plotting_Scenarios.pdf).
- Bueno de Mesquita, B. Entretien *Theory Talks #31* :
  [theory-talks.com](https://theory-talks.com/talks/31-bruce-bueno-de-mesquita).
- Scholz, J., Calbert, G., Smith, G. « Unravelling Bueno de Mesquita's group decision model »,
  *Journal of Theoretical Politics* 23(4), 2011 :
  [doi:10.1177/0951629811418142](https://doi.org/10.1177/0951629811418142).
- Hassan, H. G. « Structure, not Magic: An Open Replication and Predictability Ceiling for the
  Bueno de Mesquita Forecasting Model », SSRN, août 2026 :
  [papers.ssrn.com](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7285840).

### Rivaux disciplinaires

- Turchin, P. « Political instability may be a contributor in the coming decade », *Nature* 463, 608,
  2010 : [doi:10.1038/463608a](https://doi.org/10.1038/463608a).
- Turchin, P. et al. « The 2010 structural-demographic forecast for the 2010–2020 decade: A
  retrospective assessment », *PLOS ONE*, 2020 :
  [doi:10.1371/journal.pone.0237458](https://doi.org/10.1371/journal.pone.0237458).
- Sundstrom, S. M., Allen, C. R. « The adaptive cycle: More than a metaphor », *Ecological
  Complexity* 39, 100767, 2019 :
  [doi:10.1016/j.ecocom.2019.100767](https://doi.org/10.1016/j.ecocom.2019.100767).
- Sussmann, H. J., Zahler, R. S. « Catastrophe theory as applied to the social and biological
  sciences: A critique », *Synthese* 37, 117-216, 1978 :
  [doi:10.1007/BF00869575](https://doi.org/10.1007/BF00869575).
- Sussmann, H. J., Zahler, R. S. « A critique of applied catastrophe theory in the behavioral
  sciences », *Systems Research and Behavioral Science*, 1978 :
  [doi:10.1002/bs.3830230409](https://doi.org/10.1002/bs.3830230409).
- Zahler, R. S., Sussmann, H. J. « Claims and accomplishments of applied catastrophe theory »,
  *Nature* 269, 759-763, 1977 :
  [doi:10.1038/269759a0](https://doi.org/10.1038/269759a0).
- Isnard, C. A., Zeeman, E. C. « Some models from catastrophe theory in the social sciences », dans
  *The Use of Models in the Social Sciences*, Tavistock, 1976 :
  [chapitre](https://www.taylorfrancis.com/chapters/edit/10.4324/9780429267055-3/models-catastrophe-theory-social-sciences-isnard-zeeman).
- McAdam, D., Tarrow, S., Tilly, C. *Dynamics of Contention*, Cambridge University Press, 2001 :
  [sommaire](https://assets.cambridge.org/97805218/05889/toc/9780521805889_toc.pdf).

### Chaîne de prévision

- Gerner, D., Schrodt, P., Yilmaz, Ö., Abu-Jabr, R. *CAMEO*, 2002.
- Leetaru, K., Schrodt, P. *GDELT*, 2013.
- POLECAT — documentation :
  [doi:10.7910/dvn/lmfpip](https://doi.org/10.7910/dvn/lmfpip).
- « Evaluating Automated Event Databases for Event Forecasting: A Comparative Analysis of GDELT
  and POLECAT », *Data*, 2026 :
  [doi:10.3390/data11070158](https://doi.org/10.3390/data11070158).
- ViEWS — prévisions et modèles :
  [viewsforecasting.org](https://viewsforecasting.org/).
- Good Judgment — track record des superforecasters :
  [goodjudgment.com](https://goodjudgment.com/resources/the-superforecasters-track-record/).
- Good Judgment — comparaison avec Polymarket :
  [goodjudgment.com](https://goodjudgment.com/testing-polymarkets-most-accurate-claim/).
- Metaculus — FutureEval, printemps 2026 :
  [metaculus.com](https://www.metaculus.com/notebooks/45373/spring-2026-futureeval-analysis/).
- ForecastBench :
  [forecastbench.org](https://www.forecastbench.org/).
- « ForecastBench: A Dynamic Benchmark », 2026 :
  [PDF](https://faculty.wharton.upenn.edu/wp-content/uploads/2026/02/ForecastBench_A_Dynamic_.pdf).
- « LLM-as-a-Prophet: Understanding Predictive Intelligence with Prophet Arena », ICLR 2026 :
  [iclr.cc](https://iclr.cc/virtual/2026/poster/10009102).
- Lu, J. « Evaluating LLMs on Real-World Forecasting Against Expert Forecasters », 2025,
  arXiv:2507.04562 : [arxiv.org](https://arxiv.org/abs/2507.04562).

### Instruments et statistique

- Ragin, C. C. « Set Relations in Social Research: Evaluating Their Consistency and Coverage »,
  *Political Analysis* 14(3), 2006.
- Ragin, C. C. *QCA Research Notes* — consistance et couverture :
  [PDF](https://compasss.org/wp-content/uploads/2024/11/Research-Notes-1.pdf).
- Howard, S. R., Ramdas, A., McAuliffe, J., Sekhon, J. « Time-uniform, nonparametric, nonasymptotic
  confidence sequences », *Annals of Statistics* 49(2), 1055-1080, 2021 :
  [doi:10.1214/20-AOS1991](https://doi.org/10.1214/20-AOS1991).
- « Comparing Sequential Forecasters », *Operations Research*, 2021 :
  [doi:10.1287/opre.2021.0792](https://doi.org/10.1287/opre.2021.0792).

### Cadres de calcul

- PyCIB — Cross-Impact Balance :
  [github.com/ag-ross/pycib](https://github.com/ag-ross/pycib).
- FCMpy — Fuzzy Cognitive Maps :
  [github.com/SamvelMK/FCMpy](https://github.com/SamvelMK/FCMpy).
- pgmpy — causal and probabilistic reasoning :
  [pgmpy.org](https://pgmpy.org/).
- Metaculus `forecasting-tools` :
  [github.com/Metaculus/forecasting-tools](https://github.com/Metaculus/forecasting-tools).

### Le dépôt analysé

- `Othman-Benbrahim/alphabet-situationnel`, version 0.7.15, licence MIT. Fichiers lus :
  `README.md`, `SKILL.md`, `references/apports-theoriques.md` §16–§18, `references/validation.md`,
  `references/graphe.md`, `references/simulation.md`, `references/feuille-de-route.md`,
  `scripts/moteur.py`, `CHANGELOG.md`.
- *Audit structuré — Alphabet situationnel v0.7.11 (paquet V34)*, 31 octobre 2026, document de
  l'auteur. Utilisé pour ses constats vérifiables (§3.9, §3.10, §6.3, §6.4) et pour la liste de ses
  propres corrections (§16 des apports théoriques). Ses jugements de valeur sont cités comme des
  jugements, non comme des mesures.

---

*Document préparé le 31 octobre 2026 pour la version 0.7.15 du dépôt analysé. Les positions des
concurrents sont des reformulations, pas des citations ; les chiffres de performance sont datés et
sourcés. Aucun de ces concurrents n'est utilisé comme source de données dans le dépôt analysé.*
