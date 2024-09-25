---
title: Système de Gestion du Transport en Commun (TEC)
publishDate: 2023-12-28 00:00:00
img: /assets/air-auto-railway-transport-silhouette-260nw-2155243835.webp
img_alt: Bus prenant des passagers à un arrêt de bus en ville
description: |
  Découvrez comment gérer la montée et la descente des passagers dans les bus publics en utilisant la programmation orientée objet. Ce guide décrit le processus de portage d'une application C vers Java de manière incrémentale, en se concentrant sur la création de classes abstraites pour les véhicules et les passagers.
tags:
  - Java
  - Programmation Orientée Objet
  - Système de Transport en Commun
---

## Système de Gestion du Transport en Commun (TEC)

> Gérez efficacement les interactions des passagers dans un système de bus en utilisant Java.

Ce projet consiste à porter une application existante écrite en C vers Java, en adoptant une approche orientée objet. Le projet est conçu pour être développé de manière incrémentale au fil d'une série de travaux pratiques, en se concentrant sur la gestion de la montée et de la descente des passagers dans les bus publics.

### Prérequis

Pour démarrer ce projet, vous aurez besoin de :

- **JDK Java SE 8u221 ou supérieur** : Assurez-vous que votre Kit de Développement Java est à jour.
- **Make** : Un outil d'automatisation de la compilation qui simplifie le processus.
- **Machine Linux** : Le projet est optimisé pour un environnement Linux.

### Aperçu du Projet

L'objectif de ce projet est de gérer le processus de montée et de descente des passagers dans les bus. Un bus maintiendra une liste de passagers et les notifiera à chaque arrêt. Les passagers pourront répondre en demandant de descendre ou de changer leur arrangement de place (par exemple, assis, debout).

Le projet inclut des classes abstraites pour `Vehicule` et `Passager`. Pour différentes étapes du projet, une branche séparée avec des modèles de fabrication peut être consultée en utilisant la commande `git checkout TD{numero}factory`.

Actuellement, le projet propose plusieurs types d'interactions `Montee` (4 types) et `Arret` (5 types) qui définissent le comportement des passagers. Il y a trois types de passagers, chacun implémentant une combinaison `Montee-Arret`. L'exécution de `TestsGlobaux` permettra de tester tous les types de passagers.

### Structure du Projet

Le projet est organisé comme suit :

- **Makefile** : Script pour automatiser le processus de compilation.
- **README** : Ce document.
- **src/** : Fichiers sources pour les classes principales en Java.
- **tst/** : Fichiers de test pour tester unitairement les classes principales.
- **build/tec/** : Fichiers compilés pour le paquetage `tec`.
- **report/** : Rapport final du projet au format PDF.

### Compilation et Exécution

Suivez ces étapes pour compiler et exécuter le projet :

- **Compiler le projet** :
  ```sh
  make
