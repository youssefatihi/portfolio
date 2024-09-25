---
title: Projet de Compilation MyC-PCode
publishDate: 2024-02-25 00:00:00
img: /assets/stock-2.jpg
img_alt: Visualisation d'un processus de compilation de MyC vers P-Code
description: |
  Ce projet développe un compilateur pour un mini langage impératif nommé MyC, qui est traduit en P-Code. Le compilateur couvre les six premières phases de compilation et inclut des fonctionnalités pour automatiser la comparaison des résultats avec les solutions correctes.
tags:
  - Compilation
  - MyC
  - P-Code
  - GCC
---

## Projet de Compilation MyC-PCode

> Un projet pour développer un compilateur pour le langage MyC vers P-Code.

Ce projet vise à implémenter un compilateur pour un mini langage impératif nommé **MyC**, lequel est traduit en **P-Code**. Le compilateur actuel prend en charge les six premières phases de la compilation et gère jusqu'à l'exemple 17.

### Structure du Projet

Le projet est structuré de manière à inclure les dossiers suivants :

- **Répertoire de Correction** : Un dossier `correction` contient les solutions correctes pour tous les fichiers exemples. Un script shell `./test` compare automatiquement les résultats obtenus avec ces fichiers de correction.
  
- **Modifications apportées** : Tous les exemples du dossier `Pcode` se compilent sans erreur. Des modifications ont été faites pour corriger certains problèmes dans les fichiers d'exemples fournis. En particulier, les références à `stack[bp]+1` ont été remplacées par `stack[bp].int_value+1`.

### Instructions de Compilation

#### Compilation de MyC vers P-Code

Pour compiler un fichier MyC en P-Code, suivez ces étapes :

1. Exécutez `make` pour construire le compilateur.
2. Utilisez `./run ExX` pour compiler un exemple spécifique, où **X** correspond au numéro de l'exemple (par exemple, 01, 02, ..., 17).

#### Compilation des fichiers P-Code avec GCC

Pour compiler les fichiers P-Code avec GCC :

1. Naviguez dans le répertoire `PCode`.
2. Exécutez `make ExX` pour compiler un fichier spécifique, ou utilisez `makeall` pour compiler tous les fichiers en une seule commande.

### Contact

Pour toute question ou assistance, vous pouvez contacter le responsable du projet.

---
