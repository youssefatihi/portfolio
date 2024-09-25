---
title: Tower Defense Game Development
publishDate: 2023-04-02 00:00:00
img: /assets/tower.png
img_alt: Example from a Tower Defense game showing enemies and towers
description: |
  A Tower Defense game project focusing on functional programming techniques to create a dynamic, grid-based world where actors (enemies, towers) interact in a strategic environment. Build the game engine, define phases, and manage interactions using pure functions.
tags:
  - Game Development
  - Functional Programming
  - Tower Defense
  - TypeScript
  - Multi-Agent Systems
---

#### Tower Defense Game Development

#####  Project Overview

Tower Defense is a genre of video games where the player defends a terrain from repeated waves of enemies determined to overwhelm the player's defenses. The enemies usually follow one or more paths leading to a vulnerable point on the map (often considered as the objective), and are slowed down or blocked by towers, which act upon the enemies in various ways (elimination, blocking, slowing down, etc.).

In this project, inspired by games like *Kingdom Rush*, players can strategically place towers and characters along predefined paths to block enemies and protect their objective.

**Note:** This project emphasizes **functional programming** (purity and first-class functions) and prohibits the use of object-oriented features such as classes or the `this` keyword. Interaction during gameplay (outside of setup) is considered out-of-scope.

#####  Key Features

- **Grid-Based World**: A 2D grid where actors (towers, enemies) are placed and interact.
- **Multiple Game Phases**: Game turns consist of several phases (move, block, target, fight, etc.).
- **Functional Programming**: All game elements and interactions are driven by pure functions.
- **Autonomous Actors**: Each actor has its own decision-making function.
- **Procedural Generation**: Automatic generation of paths and environments.
- **Text-Based or HTML Visualization**: Start with text-based visualizations and evolve to an HTML page.
  
#####  Game Phases and Mechanics

- **Move Phase**: Enemies attempt to move toward the objective. Each actor can propose a movement, and the game engine handles conflicts (e.g., if multiple actors try to move to the same location).
- **Block Phase**: Towers and characters can block the path of enemies.
- **Target Phase**: Towers choose which enemies to target based on proximity or other criteria.
- **Fight Phase**: Damage calculations occur, and actors (both enemies and defenders) may be destroyed.

#####  Functional Programming Approach

The game is structured using functional programming paradigms. For example, actors are represented as immutable entities whose actions are defined by pure functions. Each function computes an intention (e.g., move, attack), and the game engine applies these intentions following specific rules.

Here is a simple example of an actor that always moves one step to the right:

```javascript
const actor = {
    pos: { x: 5, y: 7 },
    actions: {
        move: (actor, world) => { return { dx: 1, dy: 0 }; }
    }
};
```

#####  Project Architecture

```
/               -- Base directory
Makefile        -- Global Makefile
package.json    -- npm configuration file
/src            -- Source files
/tst            -- Test files
/html           -- Web files (HTML, CSS)
/dist           -- Install directory
/node_modules   -- npm directory (excluded from repository)
```

#####  Installation and Dependencies

To install the project and its dependencies, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/tower-defense.git
   cd tower-defense
   ```

2. Install the necessary dependencies using npm:
   ```bash
   npm install
   ```

3. Build the project:
   ```bash
   make build
   ```

4. Run the game in the console:
   ```bash
   make run
   ```

5. Run tests:
   ```bash
   make test
   ```

#####  Development Guidelines

This project uses the following tools and configurations:

- **TypeScript**: Write code in TypeScript. Files are compiled using `tsc` (TypeScript Compiler).
- **ESLint**: Code style and syntax verification. Run the linter with:
   ```bash
   npx eslint src tst
   ```
- **Jest**: Testing framework for running unit tests.
   ```bash
   npx jest tst/*.ts
   ```
- **Parcel**: A bundler for web projects, which can be used to serve HTML and JavaScript files for visualizing the game.
   ```bash
   npx parcel dist/index.html
   ```

#####  Game World and Actors

The game world is a 2D grid where actors (enemies, towers, and obstacles) interact. Each actor has specific characteristics such as position and available actions. The game progresses in turns, with each turn broken down into distinct phases (move, block, attack, etc.).

Example of initializing the world and actors:

```javascript
world = initializeWorld();
actors = initializeActors(world);
phases = computePhases(world, actors);
```

#####  Testing and Debugging

- Use **Jest** for writing unit tests for different game phases, actions, and the game engine.
- Ensure that the game compiles and runs smoothly using **TypeScript** and **ESLint** for code quality checks.

#####  Future Improvements

- **AI Behavior**: Add smarter AI for enemies, including pathfinding (e.g., A* algorithm) and dynamic strategy adjustments.
- **HTML Visualization**: Build an interactive HTML-based visualization to complement the text-based version.
- **New Phases**: Introduce additional game phases like healing, trading, or special abilities.
- **Procedural Generation**: Enhance the procedural world generation to create more varied and challenging maps.
