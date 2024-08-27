---
title: API de Planification d'Itinéraires sécurisés pour la Micromobilité
publishDate: 2020-03-02 00:00:00
img: /assets/WhatsApp Image 2024-08-23 at 4.15.04 p.m..jpeg
img_alt: Safe routes for micromobility devices
description: |
  Cette API vise à fournir des itinéraires sécurisés pour les utilisateurs de trottinettes électriques et de vélos sur le campus de Pessac-Talence-Gradignan, en prenant en compte des facteurs cruciaux comme le trafic, l'éclairage, et la météo.
tags:
  - API
  - Micromobilité
  - Sécurité
---

# API de Planification d'Itinéraires sécurisés pour la Micromobilité 🚲📱

## 📝 Résumé 

L'API de Planification d'Itinéraires sécurisés pour la Micromobilité vise à résoudre le problème croissant des accidents impliquant des dispositifs de micromobilité sur le campus de Pessac-Talence-Gradignan, notamment parmi les jeunes. L'objectif est de développer une API innovante capable de calculer dynamiquement des itinéraires sûrs pour les utilisateurs de trottinettes électriques et de vélos. En tenant compte de paramètres cruciaux tels que le trafic, l'éclairage, la météo et les données en temps réel, l'API fournira des itinéraires optimisés et sécurisés adaptés aux besoins spécifiques des utilisateurs. Cette initiative favorise les déplacements écologiques et sûrs tout en améliorant l'expérience globale de mobilité.

## 📋 Spécifications

Les spécifications de l'API comprennent :

- Conception/amélioration d'un algorithme de calcul d'itinéraire
- API interrogeable en temps réel
- Affichage d'informations statistiques sur les itinéraires
- Documentation complète
- Collecte de données utilisateur
- Mise à jour dynamique des itinéraires en fonction des facteurs de sécurité en temps réel
- Accessibilité sur diverses plateformes et systèmes d'exploitation
- Intégration de sources de données externes en temps réel
- Recommandations d'itinéraires personnalisées basées sur les préférences de l'utilisateur
- Fonctionnalités de notation de sécurité et de signalement d'incidents

## 🔄 Fonctionnement des Commits 

### ⚠️ Le plus important pour les commits !

Monter les changements et/ou modifications (staged changes) puis lancer : ⚠️ **./commit.sh** ⚠️ pour formater le commit correctement et lancer l'exécution automatique des tests.

### Branches & Significations :

- **feature/\<feature-name\> :** Utilisée pour le développement de nouvelles fonctionnalités.

- **develop :** Branche pour le développement quotidien, les corrections de bugs, le refactoring de code, ainsi que les tests unitaires et d'intégration.

- **main :** Branche stable où les tests système et d'acceptation sont effectués.

- **production :** Version finale du code utilisée en production.

### Méthode de Déploiement :

1. **Développement de Fonctionnalités :** Commencez par développer une fonctionnalité sur la branche feature/\<feature-name\>.

2. **Fusion avec la Branche develop :** Fusionnez la fonctionnalité développée sur feature/\<feature-name\> avec la branche develop (sans besoin de pull request).

3. **Correction des Bugs et Ajouts Mineurs :** Corrigez les bugs et effectuez des ajouts mineurs directement sur la branche develop (sans besoin de pull request), puis effectuez les tests.

4. **Pull Request vers la Branche main :** Si la branche develop est stable, ouvrez une pull request pour fusionner avec la branche main.

5. **Validation et Pull Request vers la Branche production :** Une fois les tests réussis sur la branche main, ouvrez une pull request pour fusionner avec la branche production.


## 🛠 Mise en place

Pour installer les dépendances nécessaires pour lancer le projet, suivez ces étapes :

### 0. 🚀 Setup rapide pour linux

```bash
./setup.sh
```

Puis passer directement à l'étape 5

### 1. 📦 Créer un Environnement Virtuel (Optionnel mais Recommandé)

Il est recommandé d'utiliser un environnement virtuel pour isoler les dépendances de ce projet des autres projets Python sur votre système. Vous pouvez créer un nouvel environnement virtuel en utilisant `venv` ou `conda`, selon vos préférences.

Exemple avec `venv` :
```bash
python3 -m venv venv
```

Activez ensuite l'environnement virtuel :
- Sur Linux/macOS :
```bash
source venv/bin/activate
```
- Sur Windows :
```bash
venv\Scripts\activate
```

Après avoir travaillé, vous pouvez désactiver l'environnement virtuel en utilisant la commande suivante :

```bash
deactivate
```

### 2. 📋 Installation des Dépendances

Vous pouvez installer les dépendances à partir du fichier `requirements.txt` fourni avec le projet en utilisant `pip`. Assurez-vous que vous êtes dans le répertoire racine de votre projet où se trouve le fichier `requirements.txt`.

```bash
pip install -r requirements.txt
```

### 3. ⚙️ Configuration de l'Environnement

Créer un dossier `graphml`
```bash
mkdir graphml
```

Créer un fichier .env et ajoutez les variables suivantes en les **modifiants** selon votre arborescence :
```dotenv
PATH=/chemin/vers/saferide/graphml/networkBM.graphml
PATH_UG=/chemin/vers/saferide/graphml/networkBMUG.graphml
```

### 4. Création du graphe
Avant de lancer l'application, il faut créer le graphe

```bash
python3 creation.py
```

### 5. ▶️ Lancement du Projet

Une fois les dépendances installées, l'environnement configuré et le graphe créé, vous pouvez lancer le projet en exécutant le script principal ou la commande spécifique à votre application.

```bash
python3 app.py
```

Vous pouvez ensuite tester des requêtes à l'API avec par exemple : 
```bash
curl -X POST -H "Content-Type: application/json" -d '{"orig": [44.796312, -0.576244], "dest": [44.830807, -0.578356]}' http://127.0.0.1:5000/calculate
```