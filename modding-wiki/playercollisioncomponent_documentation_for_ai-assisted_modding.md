---
title: PlayerCollisionComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:PlayerCollisionComponent
category: modding-wiki
---

# PlayerCollisionComponent Documentation

This document details the `PlayerCollisionComponent` in Noita, a crucial component for understanding and modifying how the player interacts with the game world. Understanding its properties and behaviors is essential for creating mods that alter player movement, environmental interactions, and collision-based mechanics.

## Overview of PlayerCollisionComponent

The `PlayerCollisionComponent` governs the player's physical interactions with the environment. This includes how the player collides with solid objects, how they are affected by gravity and momentum, and how they can traverse different terrain types. Modifying this component can lead to significant changes in gameplay, from altered jump heights and movement speeds to entirely new ways of interacting with the world.

## Component Properties

The `PlayerCollisionComponent` is defined within the game's entity system and can be accessed and modified through Lua scripting. Its properties control various aspects of player collision.

### Key Properties and Their Effects

| Property Name        | Type    | Description