# Analyse de l'Alphabet situationnel — Journal des versions

> Version : 0.7.15 · révision 1

> La version suit celle du dépôt analysé ; la révision compte les réécritures à version constante.
> Une entrée ne cite jamais le commit qui la contient, créé après elle : une version livrée se retrouve
> par son étiquette `vX.Y.Z`. Les corrections conservent l'entrée fautive et nomment ce qui a changé.

## 0.7.15 — révision 1 — 2026-10-31 · ce que le lecteur voit, et le concurrent nommé

Révision complète pour la version 0.7.15 du dépôt analysé, huit versions après la dernière révision.
**Aucune probabilité du dépôt ne change** : la comparaison directe des moteurs 0.7.7 et 0.7.15 sur les
2 790 conséquences de la clôture donne **0 conséquence changée**, et aucun statut de case n'a bougé
(181 Proposé, 14 Vide, 13 Documenté, 0 Attesté, identiques à la 0.7.7).

**Nouveau document.** `concurrents-directs.md` — seize concurrents en quatre cercles, plus sept instruments de calcul, ce qu'ils
promettent, ce qu'ils produisent, ce qui le prouve, l'écart décisif, et huit protocoles de départage.
Deux ajouts de périmètre par rapport à la première rédaction, dus à un audit versé par l'auteur :

- **quatre rivaux disciplinaires** que la note ne couvrait pas — cliodynamique (Turchin), panarchie
  (Holling), théorie des catastrophes (Thom, Zeeman), *Dynamics of Contention* (McAdam, Tarrow,
  Tilly). Le concurrent le plus proche est en sociologie relationnelle, pas en stratégie d'entreprise ;
- **deux instruments** — QCA (consistance et couverture, le déficit le plus net du dépôt) et
  l'inférence séquentielle (corrigée dans le dépôt en 0.7.12, après l'avoir été par l'audit).

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
