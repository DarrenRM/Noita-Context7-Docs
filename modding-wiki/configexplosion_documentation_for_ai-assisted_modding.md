---
title: ConfigExplosion Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ConfigExplosion
category: modding-wiki
---

# ConfigExplosion Documentation

This document details the `ConfigExplosion` component in Noita, a crucial element for defining and customizing explosive effects within the game. Understanding `ConfigExplosion` is essential for modders looking to create new weapons, spells, or environmental hazards that involve explosions, allowing for fine-grained control over their behavior and impact.

## Understanding ConfigExplosion

The `ConfigExplosion` component is attached to entities that produce an explosion. It governs various aspects of the explosion's behavior, including its damage, radius, visual effects, and how it interacts with the game world.

### Core Properties

The following properties are commonly found within a `ConfigExplosion` component. These are typically defined in `.xml` files within the game's data.

| Property Name        | Type    | Description