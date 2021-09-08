# battle_101

## Overview

This is a prototype of a game that I envision and that combines strategy, action, and superhero elements 

## Updates

### 2021.09.08 - Dynamic A* completed. Demo: 

## Roadmap

### Due 2021.09.13 - Finish a prototype of the game
##Requirements##
- Interface:
1. Select a posiiton or an enemy for soldiers to move to through clicking
2. Select the number of soldiers for a unit
- Arts:
3. A basic terrain and basic home camp
- Mechanisms:
4. Dynamic A* (Strategy)
5. Walking and fighting animations of soldier (Individual-level decision)
6. 1 physical attack and 1 special attack animation of player

### Due 2021.09.20 - Add basic natural language processing to the game

## Design

Broadly speaking, such a game can be broken into three components:

### Interface

Interface is the component that recevices and translates user input and eventually illustrates the output graphically after the user command is processed by the game mechanisms. A richer set of user command formats that are more human-friendly will hopefully be supported, thanks to the advances in computer vision and natural language processing, and it will certainly enhance user experience.

### Arts

Arts consist of all aspects of work needed to make the game aesthetically pleasing. Examples include making character animations and game environments look more realistic.

### Mechanisms

Mechanisms of the game define how agents in the game interact with the environment, each other, and user commands and how the environment evolves over time following the actions taken by agents. Focusing on agents, we can categorize the sources that causes an agent to take actions as the following:

#### Strategy

A strategy is a high-level command given by users. It can be an order given by a player to one of his/her soldier units to block the movement of an enemy troop. In most cases, a strategy is expected to have the highest priority among the tasks stored in the priority queue held by an agent controller program.

#### Tactic

A tactic is a means discretionaly taken by agents to maximize the goal set by the player. Once a player's army receives the order of slowing down the movement of the enemy, they need to organize their formation and collaborate in such a way that no other goals (e.g. killing as many enemy agents as possible) but the one given by the player is optimized, provided that optimizing different goals requires different actions. In practice, this part of mechanisms will likely be developed through ML-Agents.

#### Individual-level decision

An individual-level decision is a specific action taken by an individual agent and modeled by the constraints of the higher-level strategy and tactic plus some degree of freedom. In real life, the degree of freedom can have a large range such that we can vividly recall the dramas of renegade and heroism. However, it is expected that in the game individual-level degree of freedom will mostly manifest itself in animation with noise rather than decision-making. Still, the number of tactic controllers may be increased to approximate individual-level degree of freedom (meaning that instead of having 1 tactical model for every 100 soldiers, having 2, for example).
