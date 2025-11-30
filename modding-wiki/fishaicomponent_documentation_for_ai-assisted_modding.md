---
title: FishAIComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:FishAIComponent
category: modding-wiki
---

# FishAIComponent Documentation for AI-Assisted Modding

This document details the `FishAIComponent` in Noita, a crucial component for defining the behavior of fish-like entities. Understanding and modifying this component is essential for modders looking to create custom fish behaviors, integrate new fish types, or alter existing ones within the game.

## Understanding FishAIComponent

The `FishAIComponent` governs the artificial intelligence of fish entities in Noita. It dictates their movement patterns, reactions to the environment, and interactions with other game elements. By adjusting its parameters, modders can significantly influence how fish behave, from simple swimming to complex avoidance or pursuit.

### Core Functionality

The primary role of `FishAIComponent` is to provide a framework for fish AI. This includes:

*   **Movement:** Defining how fish navigate through water and other environments.
*   **Sensing:** How fish perceive their surroundings, including players, other creatures, and obstacles.
*   **Behavioral States:** Implementing different actions or reactions based on perceived stimuli.

### Key Parameters and Their Effects

The `FishAIComponent` is configured through XML files, typically within the `data/entities/animals/` directory. Modders can override or extend these configurations to change fish behavior.

Here are some of the key parameters you might encounter and their general purpose:

| Parameter Name        | Description