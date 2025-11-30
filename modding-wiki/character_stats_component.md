---
title: Character Stats Component
source: https://noita.wiki.gg/wiki/Documentation:CharacterStatsComponent
category: modding-wiki
---

# Character Stats Component

This documentation explains the `CharacterStatsComponent` in Noita, a crucial component for defining and modifying character attributes. Understanding this component is essential for modders looking to alter player or enemy stats, implement new abilities, or balance gameplay.

## Overview

The `CharacterStatsComponent` is a fundamental part of Noita's entity system, responsible for managing a wide array of numerical attributes that define a character's capabilities. This includes health, mana, movement speed, damage modifiers, and many more. By modifying the values within this component, modders can significantly impact gameplay.

## Component Structure and Properties

The `CharacterStatsComponent` is defined within entity XML files and can be accessed and manipulated via Lua scripting. It contains numerous properties, each controlling a specific character statistic.

### Key Properties

Here are some of the most commonly used properties within the `CharacterStatsComponent`:

| Property Name        | Description