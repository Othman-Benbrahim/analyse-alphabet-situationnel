# Analyse de l'Alphabet situationnel

Note de synthèse critique sur le protocole **Alphabet situationnel** (dépôt
[`Othman-Benbrahim/alphabet-situationnel`](https://github.com/Othman-Benbrahim/alphabet-situationnel),
licence MIT), version **0.7.7**, au 30 octobre 2026.

**Version de la note : 0.7.7 · révision 1 · 30 octobre 2026.**
Les trois documents d'analyse portent la même version ; la révision compte les réécritures à version
constante du dépôt analysé. **Intégrité** : `SHA256SUMS` donne l'empreinte de chaque fichier livré ;
`sha256sum -c SHA256SUMS` (ou `Get-FileHash` sous Windows) refuse un fichier modifié, ajouté ou retiré.
Une version livrée se retrouve par son étiquette `vX.Y.Z` ; aucun document ne cite le commit qui le
contient, créé après lui.

---

## Contenu du dépôt

| Fichier | Objet |
|---|---|
| [`analyse-alphabet-situationnel.md`](analyse-alphabet-situationnel.md) | la note : état des lieux, fonctionnement, axiome, littérature, comparaison, bilan, ce qui reste |
| [`comprendre-l-alphabet-situationnel.md`](comprendre-l-alphabet-situationnel.md) | la vulgarisation : la moitié sémiotique, la moitié mathématique, et comment l'une conditionne l'autre |
| [`CHANGELOG.md`](CHANGELOG.md) | le journal des versions de la note, révision par révision |
| `SHA256SUMS` | l'empreinte des fichiers livrés |

Il n'y a pas de code ici : le moteur, les références et les bases restent dans le dépôt analysé. Les
chiffres cités sont tous reproductibles par ses commandes, et les commandes sont données.

---

## Comment cette note est versionnée

Le dépôt analysé suit un versionnement sémantique `MAJEUR.MINEUR.CORRECTIF`, et la note s'y aligne
plutôt que d'inventer une numérotation concurrente. Trois règles suffisent :

| Changement | Effet sur la note | Exemple |
|---|---|---|
| **Correctif** — un chiffre, une coquille, une référence corrigés sans changer une conclusion | révision +1, version inchangée | 0.7.7 · révision 1 → 0.7.7 · révision 2 |
| **Mineur** — le dépôt analysé change de version mineure | version alignée, révision remise à 1 | 0.7.4 → 0.7.7 |
| **Majeur** — le plan, le verdict ou la thèse de la note changent | version majeure de la note, indépendante du dépôt | 1.0.0 |

Deux conséquences pratiques. D'abord, une note ne peut pas être « à jour » d'une version qu'elle ne
nomme pas : chaque document commence par la version du dépôt qu'il décrit. Ensuite, une correction ne
réécrit jamais l'histoire : `CHANGELOG.md` conserve l'entrée fautive et son motif de correction, comme
le journal du dépôt analysé conserve ses propres erreurs.

**Quand une nouvelle révision se justifie.** Trois événements seulement : les premiers cas réels actifs,
le franchissement du jalon V4, ou une décision d'auteur qui change un `p`. En dehors de ces cas, les
chiffres de structure — 208 cases, 66 transitions, 181 « Proposé » — changent peu et la note reste
valable. Une révision purement documentaire reste possible, mais elle ne prétend pas mesurer autre chose.

---

## Ce que contient la note

1. **État des lieux** — ce que le dépôt est, ce qu'il contient, ce qu'il sait faire, ce qu'il ne sait pas.
2. **Fonctionnement** — sept gestes, un exemple fil rouge, un lexique, ce que l'outil ne fait pas.
3. **L'axiome** — les quatre sous-axiomes, leur origine dans la littérature, et le problème central de la
   classe de référence, instrumenté depuis 0.7.3.
4. **Dix expériences abouties** — du codage des actes au modèle de langue, avec ce que chacune prouve et
   ne prouve pas.
5. **Comparaison** — même chaîne, deux ontologies ; ce que chaque famille peut apporter.
6. **Ce que ça dit du dépôt** — cinq forces, trois faiblesses, un mur.
7. **Ce qui reste** — ce que les versions 0.7.3 à 0.7.7 ont fermé, ce qui reste ouvert, par priorité.
8. **Sources**, puis deux annexes : le journal des vérifications exécutées, et le tableau des changements
   depuis la révision précédente.

## Ce que contient la vulgarisation

Un document séparé, écrit pour être lu sans connaissance préalable. Il expose d'abord la **partie
sémiotique** — ce qui compte comme signe, comment un fait ancre une carte, pourquoi F n'est pas une
intensité —, puis la **partie mathématique** — ce qui est calculé, avec quels nombres et quelles
garanties —, et enfin le **conditionnement de l'une par l'autre** : sans signe, pas de lettre ; sans
lettre, pas d'état ; sans état, le moteur ne calcule qu'une fréquence par défaut. Il termine par un
exemple complet et par les trois confusions les plus fréquentes.

---

## Ce que cette note n'est pas

- **Ce n'est pas une validation.** Aucune performance prédictive n'est acquise, et la note le répète
  chaque fois que le sujet risque de prêter à confusion.
- **Ce n'est pas un audit d'intégrité.** L'audit et les autotests du dépôt vérifient la forme et le
  recoupement interne ; ils ne certifient ni la vérité des faits ni l'utilité scientifique de l'alphabet.
- **Ce n'est pas une revue de littérature exhaustive.** Les dix expériences citées sont celles qui
  éclairent le choix ontologique du dépôt, pas l'ensemble du champ.
- **Les chiffres de démonstration ne mesurent rien.** Ils proviennent d'une base **entièrement fictive**
  (`--demo`) : ils illustrent une mécanique de calcul, jamais une performance.
- **Le versionnement n'est pas une preuve de fraîcheur.** Un numéro identique ne garantit pas que le
  dépôt n'a pas changé sous le même numéro ; `SHA256SUMS` et l'étiquette de version le garantissent,
  pas la lecture de ce fichier.

---

## Comment les chiffres ont été obtenus

Toutes les valeurs citées ont été produites par le moteur du dépôt, à sa version 0.7.7 :

```
python3 scripts/moteur.py audit      # intégrité du paquet
python3 scripts/moteur.py autotest   # 126 tests de régression
python3 scripts/moteur.py bilan      # avancement mesuré sur la feuille de route
python3 scripts/moteur.py calculer … --demo   # démonstration, base fictive
python3 scripts/moteur.py sonde … --demo --tirages 200   # paramètres contre le hasard
python3 scripts/moteur.py confronter assets/cas-reels.jsonl   # matrice contre observations
```

Deux mesures ne figurent pas telles quelles dans la sortie standard et ont été recalculées par appel
direct des fonctions publiques du moteur : l'effet des cartes et de l'homologie sur cinq événements de
démonstration (mesuré en 0.7.4, probabilités inchangées depuis), et la fragilité de niveau sur une base
synthétique de deux cas stricts et trois cas larges. Les valeurs figurent en annexe A de la note, avec la
commande ou la construction correspondante.

Une réserve d'environnement : six autotests du dépôt écrivent dans le dossier temporaire du système. Sous
un bac à sable qui refuse l'écriture et le `chmod` à cet endroit, ils échouent ; ils ne signalent pas un
défaut du code. C'est le cas de l'exécution qui a produit cette révision : 120 tests passent, 6 échouent
sur `PermissionError`. La note le précise en annexe A plutôt que de le taire.

---

## Version couverte et mises à jour

| Version analysée | Date | Autotests | Révision de la note | Événement déclencheur |
|---|---|---|---|---|
| 0.7.2 | 27 octobre 2026 | 103 | 1 | note initiale |
| 0.7.3 | 29 octobre 2026 | 111 | 1 | audit d'ingénierie : la lecture contrôlée avant le chiffre |
| 0.7.4 | 29 octobre 2026 | 115 | 1 | version de preuve : sceau de dossier, partage daté, placebo, plancher A7 |
| **0.7.7** | **30 octobre 2026** | **126** | **1** | paramétrer avant de mesurer : seuils séparés, V4 absolu et testé, confrontation et sonde |

Les versions 0.7.5 et 0.7.6 ne sont pas couvertes par une révision séparée : la présente révision les
traite ensemble, parce qu'elles ne changent aucune probabilité et que leurs apports — confrontation,
tests d'écart, sonde — se lisent mieux comme un seul mouvement. Le détail figure au `CHANGELOG.md`.
La mention « révision 1 » des versions antérieures est rétroactive : elle désigne la première rédaction
à cette version, le compteur de révision n'ayant été introduit qu'avec la 0.7.7.

---

## Publier une révision

Cinq gestes, dans cet ordre, pour que la livraison soit vérifiable comme celle du dépôt analysé :

1. **Mettre à jour les en-têtes** des trois documents : version, révision, date.
2. **Rejouer les commandes** de la section précédente et reporter les valeurs obtenues en annexe A ;
   aucune valeur n'est recopiée d'une révision antérieure sans être marquée comme telle.
3. **Ajouter l'entrée** correspondante dans `CHANGELOG.md`, sans réécrire les entrées passées.
4. **Régénérer `SHA256SUMS`**, puis vérifier par `sha256sum -c SHA256SUMS`.
5. **Étiqueter** `vX.Y.Z` et publier une release avec `SHA256SUMS` en pièce jointe.

Un manifeste ne peut pas contenir sa propre empreinte : c'est pourquoi il couvre les documents et non
lui-même. Sur GitHub, l'étiquette et la release sont la référence ; en l'absence de signature, le niveau
d'assurance est celui du compte qui publie.

---

## Conventions de lecture

- Les commandes sont données pour un shell POSIX (`python3`) ; sous Windows, `python` suffit.
- Les citations de règles renvoient au dépôt analysé : `A6`, `A7`, `T2`, `P1`… désignent ses règles
  numérotées, pas celles de cette note.
- Les chiffres en pourcentage sont arrondis à une décimale ; les valeurs non arrondies se lisent dans la
  sortie `--json` du moteur.
- Le registre est neutre : la note parle du dépôt et de son auteur à la troisième personne, pour rester
  lisible hors du dialogue dans lequel elle a été écrite.
- **`p` n'est pas une probabilité calibrée.** C'est une fréquence conditionnelle expérimentale, dont le
  niveau ρ dit la provenance, pas la fiabilité. La vulgarisation explique pourquoi cette distinction
  n'est pas une coquetterie de vocabulaire.

---

## Licence

Le dépôt analysé est distribué sous licence MIT. Le présent texte est un document distinct : sa licence
reste à trancher par son auteur — CC BY 4.0 est la suggestion la plus simple si l'objection et la
réutilisation avec attribution sont souhaitées.

## Citation

> Analyse de l'Alphabet situationnel, version 0.7.7, révision 1, 30 octobre 2026.
