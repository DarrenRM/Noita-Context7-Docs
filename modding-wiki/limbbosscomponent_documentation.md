---
title: LimbBossComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:LimbBossComponent
category: modding-wiki
---

# LimbBossComponent Documentation

This document details the `LimbBossComponent` in Noita, a crucial component for defining and managing boss-like entities with distinct limb behaviors. Understanding this component is essential for modders aiming to create custom boss enemies, modify existing ones, or implement complex AI behaviors involving segmented entities.

## LimbBossComponent Overview

The `LimbBossComponent` is a core component used in Noita's entity system to define entities that function as "bosses" with multiple, potentially independent, "limbs." These limbs can have their own behaviors, health, and interactions, contributing to a more dynamic and challenging boss encounter. This component allows for intricate boss designs by enabling the management of these separate parts.

### Key Concepts

*   **Boss Entity:** The primary entity that houses the `LimbBossComponent` and acts as the central point of control or health for the entire boss.
*   **Limb Entities:** Separate entities that are designated as "limbs" of the boss. These limbs are typically linked to the boss entity and can perform specific actions or have unique properties.
*   **Limb Management:** The `LimbBossComponent` handles the logic for how the boss entity interacts with its limbs, including their creation, destruction, health tracking, and potential AI behaviors.

## Component Properties

The `LimbBossComponent` has several properties that can be configured within an entity's XML definition to customize its behavior.

### `limbs` Property

This property is a list of limb definitions, each specifying a particular limb's characteristics and how it's associated with the boss.

| Property Name        | Type      | Description