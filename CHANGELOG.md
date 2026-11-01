# Analyse de l'Alphabet situationnel — Journal des versions

> Version : 0.7.15 · révision 1

> La version suit celle du dépôt analysé ; la révision compte les réécritures à version constante.
> Une entrée ne cite jamais le commit qui la contient, créé après elle : une version livrée se retrouve
> par son étiquette `vX.Y.Z`. Les corrections conservent l'entrée fautive et nomment ce qui a changé.

## Document ajouté · `protocole.md` — 2026-11-01 · le mode d'emploi, aligné sur la 0.7.30

**La révision de la note reste 0.7.15 · révision 1**, et aucune de ses conclusions ne change : les quatre
documents d'analyse n'ont pas été touchés. L'entrée est datée séparément parce qu'elle ajoute un document,
non une révision — et parce que ce document porte sur une autre version du dépôt analysé.

**Nouveau document.** [`protocole.md`](protocole.md) — le protocole adopté, ce qu'il reste à faire, et
l'étude d'accord détaillée à l'intention des futurs collaborateurs. Aligné sur `alphabet-situationnel`
**0.7.30** (`v0.7.30`), vérifié le 1er novembre 2026 sur un clone propre : `audit` conforme (47 fichiers
au manifeste, 208 statuts, 350 renvois §), `autotest` 155 tests OK, `bilan` 0 cas actif. C'est le seul
document du dépôt aligné sur la 0.7.30 ; l'écart avec la 0.7.15 ne porte sur aucun `p`.

**Ce qu'il contient.**

- le protocole adopté : la chaîne en sept gestes, les huit règles qui portent l'engagement (A1, A3, A4, A6,
  A7, B3, B5, V4), l'état mesuré, et le protocole de cette note ;
- ce qu'il reste à faire, ordonné, avec la dépendance qui rend l'ordre non négociable — l'étude d'accord
  bloque V4, qui bloque toute conclusion ;
- **l'étude d'accord en détail** : la décomposition de la phrase du programme en cinq conditions explicites
  et une sortie implicite ; les quatre fonctions et le droit de les cumuler ; l'unité de mesure (la
  décision carte × strate × état, pas le cas) ; les coefficients et les seuils ; les six verdicts ; le
  matériel et le problème d'ordre (la base est vide, l'étude la crée) ; la procédure en onze étapes
  datées ; les deux accords à ne pas confondre — initial et prospectif ; les six échecs prévisibles ; les
  six limites ; et un gabarit de fiche d'étude ;
- le tiers nommé : ce qu'il exécute, ce qu'il ne fait pas, ce que son indépendance doit être et comment
  elle se publie, la limite que le protocole déclare lui-même (« le codeur ne lance jamais le calcul »
  est invérifiable) ;
- la relecture par un méthodologue extérieur : une grille de douze questions, ce qu'il ne fait pas, et les
  trois issues d'un rapport — défaut de texte, valeur gelée avant l'épisode 1, valeur gelée après ;
- la liste de contrôle de l'épisode 1, en treize lignes avec leur preuve ;
- deux annexes : les commandes citées, et un lexique pour un collaborateur non méthodologue.

**Une précision, parce qu'elle est le point le plus utile du document.** La consigne de l'auteur — « codés
par deux personnes » — est plus stricte que la règle A4, qui autorise un modèle de langage comme l'un des
deux codeurs. Le document retient la consigne, et donne la raison que A4 donne elle-même : un modèle
anthropomimétique produit les produits observables de la lecture humaine que la lecture ait eu lieu ou
non. Un accord humain–modèle se publie à part, jamais comme un κ.

**Une correction de fait, constatée en passant.** Le manifeste publié `SHA256SUMS` **ne vérifiait pas**
contre les fichiers livrés : trois documents que cette entrée n'a pas touchés
(`analyse-alphabet-situationnel.md`, `concurrents-directs.md`, `comprendre-l-alphabet-situationnel.md`)
portaient une empreinte différente de celle qui était publiée, et `sha256sum -c` les refusait. La cause la
plus probable est une réédition par l'interface web de GitHub, qui réécrit les fins de ligne après
l'établissement du manifeste. Le manifeste est régénéré et **vérifie** désormais, ses six fichiers
compris. Aucune conclusion, aucun chiffre et aucun statut de case n'est en cause ; seule la prétention
d'intégrité était fausse, et elle vaut d'être consignée parce que la note elle-même avertit qu'« un
numéro identique ne garantit pas que le dépôt n'a pas changé sous le même numéro ». `protocole.md` §1.5
en tire une règle : vérifier le manifeste **après** chaque envoi, pas seulement avant.

**Fichiers touchés.** `protocole.md` (nouveau), `README.md` (table des fichiers, alignement déclaré,
section de présentation du document), `CHANGELOG.md` (cette entrée), `SHA256SUMS` (régénéré et vérifié,
six fichiers).

## 0.7.15 — révision 1 — 2026-10-31 · ce que le lecteur voit, et le concurrent nommé

Révision complète pour la version 0.7.15 du dépôt analysé, huit versions après la dernière révision.
**Aucune probabilité du dépôt ne change** : la comparaison directe des moteurs 0.7.7 et 0.7.15 sur les
2 790 conséquences de la clôture donne **0 conséquence changée**, et aucun statut de case n'a bougé
(181 Proposé, 14 Vide, 13 Documenté, 0 Attesté, identiques à la 0.7.7).

**Nouveau document.** `concurrents-directs.md` — seize concurrents en quatre cercles, plus neuf instruments et méthodes, ce qu'ils
promettent, ce qu'ils produisent, ce qui le prouve, l'écart décisif, et neuf protocoles de départage.
Deux ajouts de périmètre par rapport à la première rédaction, dus à un audit versé par l'auteur :

- **quatre rivaux disciplinaires** que la note ne couvrait pas — cliodynamique (Turchin), panarchie
  (Holling), théorie des catastrophes (Thom, Zeeman), *Dynamics of Contention* (McAdam, Tarrow,
  Tilly). Le concurrent le plus proche est en sociologie relationnelle, pas en stratégie d'entreprise ;
- **deux instruments** — QCA (consistance et couverture, le déficit le plus net du dépôt) et
  l'inférence séquentielle (corrigée dans le dépôt en 0.7.12, après l'avoir été par l'audit).

**Troisième ajout, §5.2 : SenseMaker, et c'est le cas d'espèce.** L'instrument de Snowden n'est pas un
rival de même promesse : il ne produit ni probabilité ni transition, et il ne se score pas. Il conteste
une chose plus grave — **qui a le droit de dire ce qu'un fait signifie**. Il fait signifier les acteurs
eux-mêmes, par des micro-récits situés dans un cadre de signification, et refuse par principe que le
collecteur soit aussi l'interprète. Contre l'Alphabet, l'objection n'est donc pas « votre probabilité est
fausse » mais « la lecture n'est pas votre travail » — c'est-à-dire exactement la position de repli que la
note recommandait (« caractériser des situations »). Le repli ne protège pas : il place le dépôt au centre
du débat. Le dépôt avait repéré SenseMaker d'une ligne au §14.3 de ses apports théoriques
(« signification par les acteurs contre codeur extérieur ») ; cette révision en fait la seule objection
**de légitimité** du corpus. Et le seul cas où aucun des deux camps ne peut trancher par un chiffre,
puisque SenseMaker ne publie aucune mesure de sa propre fiabilité. Ce qui en sort : un seul pont
défendable, la carte INCERTITUDE, et un protocole de plus au banc d'essai (n° 9), qui ne compare pas deux
κ mais une **divergence de contenu**.

**Correction après lecture du wiki de Cynefin (page `Cases`, notice `SenseMaker`) — §5.3 ajouté.** Une
première rédaction disait de SenseMaker : « pratique de terrain étendue ; littérature académique
critique ». **Inexact dans les deux termes**, et corrigé :

- la bibliographie de référence compte **une trentaine d'articles évalués par les pairs** (santé
  publique, développement rural, climat, gouvernance, réfugiés, démocratie délibérative) — ce n'est pas
  une littérature critique, c'est une littérature d'**applications** ;
- il existe au moins un **échec documenté par ses propres praticiens** (projet Triple-S, IRC, Ghana et
  Ouganda : abandon après 18 mois, « aucun éclairage unique ou nouveau »), ce que l'Alphabet n'a pas —
  mais il n'a rien non plus qui puisse échouer ;
- les praticiens eux-mêmes écrivent que **les triades ne supportent pas d'inférence statistique**
  (donnée compositionnelle : 33/33/33 au centre ne distingue pas « tout compte autant » de « tout compte
  peu ») ; et le wiki **met en garde contre la sur-lecture** des motifs émergents, « plus qu'indicatifs » ;
- les articles de développement d'instrument rapportent des validations sur 8 puis 10 personnes, et
  **aucune mesure de la fiabilité de l'auto-signification** (accord entre narrateurs, test-retest à
  trente jours) n'a été trouvée.

**Le résultat de cette correction, et c'est le point le plus utile de la révision.** Chaque déploiement a
son **propre** cadre de signification, conçu pour son contexte : c'est le choix qui donne la pertinence
locale et qui **interdit d'accumuler**. Les deux instruments sont donc des images miroir — SenseMaker a
des cas sans base, l'Alphabet a une base sans cas — et chacun a payé le prix de son pari. Aucun ne peut
revendiquer que son choix est meilleur, faute d'avoir produit la chose qui le démontrerait.

**Ce que la note intègre de la période 0.7.8–0.7.15.**

- **En-tête et compteurs** : 149 autotests (143 passent sous bac à sable, 6 refus d'écriture
  temporaire), 47 fichiers au manifeste, 248 renvois §, 4 571 lignes, 51 fichiers suivis.
- **Quatorze instruments** autour du calcul au lieu de six : comparateur externe aveugle (0.7.8),
  accord κ/PABAK (0.7.9), rejets et concessions (0.7.9), garantie de support (0.7.10), clôture
  (0.7.11), paire de résultats et bande d'horizon (0.7.12), variantes de codage (0.7.13), noyau
  joint (0.7.14).
- **Le résultat le plus dur est intégré** : `homologie_discernable = false`. Sur la démonstration,
  `p` = 22,0 % tombe dans la plage à 90 % du placebo (9,8–34,3 %) ; le moteur écrit que la sélection
  des homologues ne fait pas mieux que des cas tirés au hasard. Cette lecture remplace la lecture
  favorable du +1,8 point qui figurait seule en 0.7.7.
- **Le défaut de V4 et sa correction** : le test exact à effectif fixe sur un journal croissant gonfle
  l'erreur de type I quand on relit le journal. Un processus e (`e_processus`, `v4.sequentiel`) est
  publié depuis 0.7.12, à côté du statut, sans le modifier.
- **L'objet calculé** : bloc `modele` (estimande, pseudo-vraisemblance, quotient, produit des λ),
  matrice asymétrique 12/8/46, aucune loi jointe garantie, matrice sans inhibition.
- **Six forces au lieu de cinq** : la sixième est « trois supériorités structurelles sur des rivaux
  nommés » — décomposabilité contre Panarchy, marqueur indépendant contre la théorie des catastrophes,
  provenance ρ contre Tetlock, QCA et ViEWS. Elles sont écrites dans le dépôt depuis 0.7.12 et
  absentes de la note précédente.
- **Quatre faiblesses au lieu de trois** : la quatrième est le rapport entre la surface théorique et la
  portance inférentielle — 16 cartes, 13 strates, 20 références et 4 571 lignes pour trois nombres
  postulés (λ = 3 / 1,8 / 1,2), et un filtre de preuve dont l'effet mesuré est de +0,7 point.
- **Section 7.1 étendue** de 19 à 32 points fermés, avec un avertissement : trente-deux défauts de
  méthode fermés, zéro défaut empirique.
- **Priorités** : le test à trois bras passe en P0, la table *Dynamics of Contention* et la mesure de
  consistance et couverture entrent en P1.
- **Annexe A rejouée** sur la version courante, avec trois vérifications nouvelles : déterminisme de la
  clôture, conservation des 2 790 conséquences entre 0.7.7 et 0.7.15, et noyau joint.
- **Annexe B refaite** (0.7.7 → 0.7.15), sans réécrire l'annexe précédente.

**Une réserve consignée, non corrigée.** Le journal du dépôt annonce depuis la 0.7.9 une empreinte de
clôture `b1a592c8…` « identique à la 0.7.9 ». La 0.7.15 rend `b8d346ea…`. La clôture est déterministe et
aucune conséquence n'a changé : le calcul est stable, l'empreinte publiée ne se reproduit pas. La note
le dit en annexe A et s'appuie sur la comparaison directe, qui est plus forte.

**Vulgarisation.** Mise à jour pour la 0.7.15 : dix garde-fous au lieu de six, horizon publié à une,
trois et six fenêtres, homologie discernable expliquée en mots ordinaires, processus e expliqué sans
formule, et une cinquième confusion ajoutée (« un chiffre au-dessus du hasard est un résultat »).

**Ce qui n'a pas changé, et qu'il faut redire.** 0 cas actif, 0 « Attesté », κ non mesuré, V4 non
commencé, aucune calibration prospective. Le dépôt a fermé trente-deux défauts de méthode et zéro défaut
empirique. C'est un progrès de méthode, pas de connaissance.

## 0.7.7 — révision 1 — 2026-10-30 · paramétrer avant de mesurer

Révision complète pour la version 0.7.7 du dépôt analysé. **Aucune probabilité du dépôt ne change**
entre 0.7.4 et 0.7.7 ; ce qui change est la manière de les publier, de les tester et de les juger.

- **Note** : en-tête versionné, annexe B refaite (0.7.4 → 0.7.7), annexe A rejouée sur la version
  courante. 126 autotests (120 passent sous bac à sable, 6 refus d'écriture temporaire), 176 renvois §,
  181 Proposé / 14 Vide / 13 Documenté, 14/16 cases traitées en strate 7.
- **Ce qui change dans la lecture de la démonstration** : l'écart aux cartes (+10,0 points) n'est plus
  présenté comme un effet, mais comme **non interprétable** — l'a priori n'est pas ancré (17,1
  observations pondérées < 20). Le placebo reste à +1,8 point.
- **Nouveaux instruments** : `confronter` (0.7.5), `sonde` (0.7.6), taille effective de Kish, couverture
  des arêtes ; le jalon V4 devient absolu (2,5 points), testé (signe), à effectif calculé
  max(50, n(σ̂)) ; questions discriminantes et double rapport.
- **Vulgarisation** : premier document `comprendre-l-alphabet-situationnel.md`, en trois parties —
  sémiotique, mathématique, conditionnement de l'une par l'autre.
- **Versionnement** : `SHA256SUMS` et règles de numérotation ajoutés.

## 0.7.4 — révision 1 — 2026-10-29 · version de preuve

- Version analysée : 0.7.4 ; 115 autotests ; 131 renvois § ; 49 fichiers au manifeste.
- Dossier de lecture scellé exigé pour V4, partage apprentissage/test daté, placebo d'homologie,
  plancher de recherche A7 ; décision 5 (atténuation de λ) réservée.
- La note passe de « trois forces » à « quatre forces » et documente le problème de la classe de
  référence comme instrumenté.

## 0.7.3 — révision 1 — 2026-10-29 · la lecture contrôlée avant le chiffre

- Version analysée : 0.7.3 ; 111 autotests ; 131 renvois §.
- Dossier de lecture, bande de classe, fragilité de niveau, sources du calcul et propagation
  inter-strates affichées.
- Correction de six défauts signalés par l'audit d'ingénierie ; la note distingue désormais ce que le
  moteur contrôle et ce qu'il laisse au jugement.

## 0.7.2 — révision 1 — 2026-10-27 · note initiale

- Version analysée : 0.7.2 ; 103 autotests.
- Premier état des lieux : 16 cartes, 13 strates, 208 cases, 66 transitions, 0 cas actif.
- Plan conservé depuis : état des lieux, fonctionnement, axiome, littérature, comparaison, bilan,
  recommandations.
