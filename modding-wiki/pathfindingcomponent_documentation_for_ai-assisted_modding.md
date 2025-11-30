---
title: PathFindingComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:PathFindingComponent
category: modding-wiki
---

# PathFindingComponent Documentation for AI-Assisted Modding

This documentation covers the `PathFindingComponent` in Noita, a crucial component for entities that need to navigate the game world. Understanding its properties and how to configure it is essential for modders aiming to create intelligent AI behaviors for custom entities or modify existing ones.

## Understanding PathFindingComponent

The `PathFindingComponent` dictates how an entity finds its way through the game environment. It relies on a grid-based pathfinding system, typically A* search, to determine the shortest and most efficient route between two points. Modding this component allows for fine-grained control over entity movement, obstacle avoidance, and target acquisition.

### Core Properties

The `PathFindingComponent` has several key properties that can be adjusted in entity XML files. These properties influence the pathfinding behavior, including the cost of movement, the detection radius, and the maximum distance the entity will attempt to pathfind.

| Property Name        | Type    | Description