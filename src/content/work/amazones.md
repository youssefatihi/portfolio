---
title: Le Jeu des Amazones
publishDate: 2023-04-22 00:00:00
img: /assets/amazons_game.png
img_alt: Plateau du Jeu des Amazones montrant des pièces et des flèches
description: |
  Amazon est une implémentation avancée du jeu des Amazones, combinant des algorithmes sophistiqués avec une représentation graphique efficace. Ce projet explore des stratégies innovantes dans un contexte de jeu complexe et spatialement riche, offrant une plateforme pour tester et développer des algorithmes d'intelligence artificielle avancés.
tags:
  - C
  - Théorie des Graphes
  - Optimisation
  - GSL
---

### Jeu des Amazones - Projet de C

##### Description
Ce projet implémente le jeu des Amazones, un jeu de stratégie pour deux joueurs. Il comprend un serveur de jeu et des clients qui s'affrontent sur un plateau représenté par un graphe.

##### Fonctionnalités
- Serveur de jeu configurable
- Clients modulaires chargés dynamiquement
- Différentes formes de plateau (carré, donut, trèfle, huit)
- Taille de plateau variable
- Utilisation de la bibliothèque GSL pour la gestion des graphes

##### Prérequis
- GCC
- GNU Scientific Library (GSL) version 2.6 ou supérieure
- Make

##### Installation

1. Clonez le dépôt :
   ```
   git clone [URL_DU_DEPOT]
   cd [NOM_DU_PROJET]
   ```

2. Compilez le projet :
   ```
   make build
   ```

3. Installez les exécutables :
   ```
   make install
   ```

##### Utilisation

Lancez le serveur avec deux clien :
```
./install/server -m [M] -t [T] ./install/player1.so ./install/player2.so
```
- `-m [M]` : Spécifie la largeur du plateau (M ≥ 5)
- `-t [T]` : Spécifie la forme du plateau (c: carré, d: donut, t: trèfle, 8: huit)

##### Structure du projet
```
/
├── Makefile
├── src/
│   ├── server.c
│   ├── player1.c
│   ├── player2.c
│   ├── graph_t.c
│   ├── helpers.c
│   ├── server_t.c
│   └── alltests.c
└── install/
    ├── server
    ├── alltests
    ├── player1.so
    └── player2.so
```

##### Compilation et tests

- Compiler le projet : `make build`
- Exécuter les tests : `make test`
- Nettoyer les fichiers compilés : `make clean`

##### Configuration de la GSL

Le projet utilise la GSL. Si la GSL n'est pas dans le chemin standard, utilisez :
```
GSL_PATH=/chemin/vers/gsl make
```