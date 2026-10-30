# Analyse de l'Alphabet situationnel

Note de synthèse critique sur le protocole **Alphabet situationnel** (dépôt
[`Othman-Benbrahim/alphabet-situationnel`](https://github.com/Othman-Benbrahim/alphabet-situationnel),
licence MIT), version **0.7.4**, au 29 octobre 2026.

---

## Contenu du dépôt

| Fichier | Objet |
|---|---|
| [`analyse-alphabet-situationnel.md`](analyse-alphabet-situationnel.md) | la note : état des lieux, fonctionnement, axiome, littérature, comparaison, bilan, ce qui reste |

Un seul document, volontairement. Il n'y a pas de code ici : le moteur, les références et les bases
restent dans le dépôt analysé.

---

## Ce que contient la note

1. **État des lieux** — ce que le dépôt est, ce qu'il contient, ce qu'il sait faire, ce qu'il ne sait pas.
2. **Fonctionnement** — sept gestes, un exemple fil rouge, un lexique, ce que l'outil ne fait pas.
3. **L'axiome** — les quatre sous-axiomes, leur origine dans la littérature, et le problème central de la
   classe de référence, désormais instrumenté.
4. **Dix expériences abouties** — du codage des actes au modèle de langue, avec ce que chacune prouve et
   ne prouve pas.
5. **Comparaison** — même chaîne, deux ontologies ; ce que chaque famille peut apporter.
6. **Ce que ça dit du dépôt** — quatre forces, trois faiblesses, un mur.
7. **Ce qui reste** — ce que les versions 0.7.3 et 0.7.4 ont fermé, ce qui reste ouvert, par priorité.
8. **Sources**, puis deux annexes : le journal des vérifications exécutées, et le tableau des changements
   depuis la version précédente de la note.

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

---

## Comment les chiffres ont été obtenus

Toutes les valeurs citées ont été produites par le moteur du dépôt, à sa version 0.7.4 :

```
python3 scripts/moteur.py audit      # intégrité du paquet
python3 scripts/moteur.py autotest   # 115 tests de régression
python3 scripts/moteur.py bilan      # avancement mesuré sur la feuille de route
python3 scripts/moteur.py calculer … --demo   # démonstration, base fictive
```

Deux mesures ne figurent pas telles quelles dans la sortie standard et ont été recalculées par appel
direct des fonctions publiques du moteur : l'effet des cartes et de l'homologie sur cinq événements de
démonstration, et la fragilité de niveau sur une base synthétique de deux cas stricts et trois cas
larges. Les valeurs figurent en annexe A, avec la commande ou la construction correspondante.

Une réserve d'environnement : six autotests du dépôt écrivent dans le dossier temporaire du système. Sous
un bac à sable qui refuse l'écriture et le `chmod` à cet endroit, ils échouent ; ils ne signalent pas un
défaut du code. La note le précise en annexe A plutôt que de le taire.

---

## Version couverte et mises à jour

| Version analysée | Date | Autotests | Événement déclencheur |
|---|---|---|---|
| 0.7.2 | 27 octobre 2026 | 103 | note initiale |
| 0.7.3 | 29 octobre 2026 | 111 | audit d'ingénierie : la lecture contrôlée avant le chiffre |
| **0.7.4** | **29 octobre 2026** | **115** | version de preuve : sceau de dossier, partage daté, placebo, plancher A7 |

Une nouvelle révision de la note se justifie si l'un de ces trois événements survient : la décision
réservée sur l'atténuation des multiplicateurs par la qualité de l'ancrage ; les premiers cas réels
actifs ; le franchissement du jalon V4. En dehors de ces cas, les chiffres de structure (208 cases,
66 transitions, 182 « Proposé ») changent peu et la note reste valable.

---

## Conventions de lecture

- Les commandes sont données pour un shell POSIX (`python3`) ; sous Windows, `python` suffit.
- Les citations de règles renvoient au dépôt analysé : `A6`, `A7`, `T2`, `P1`… désignent ses règles
  numérotées, pas celles de cette note.
- Les chiffres en pourcentage sont arrondis à une décimale ; les valeurs non arrondies se lisent dans la
  sortie `--json` du moteur.
- Le registre est neutre : la note parle du dépôt et de son auteur à la troisième personne, pour rester
  lisible hors du dialogue dans lequel elle a été écrite.

---

## Licence

Le dépôt analysé est distribué sous licence MIT. Le présent texte est un document distinct : sa licence
reste à trancher par son auteur — CC BY 4.0 est la suggestion la plus simple si l'objection et la
réutilisation avec attribution sont souhaitées.

## Citation

> Analyse de l'Alphabet situationnel, version 0.7.4, 29 octobre 2026.
