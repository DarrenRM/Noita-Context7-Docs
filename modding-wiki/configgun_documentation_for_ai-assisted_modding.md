---
title: ConfigGun Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ConfigGun
category: modding-wiki
---

# ConfigGun Documentation

This document provides a comprehensive guide to Noita's ConfigGun, a powerful tool for dynamically modifying game configurations and entity properties. Understanding the ConfigGun is essential for advanced modding, allowing for complex in-game adjustments, custom spell behaviors, and intricate entity interactions.

## Introduction to ConfigGun

The ConfigGun is an in-game item that allows players to modify various game parameters and entity properties on the fly. It operates by targeting entities and applying specific configuration changes. This functionality is invaluable for modders who want to create dynamic gameplay experiences, test configurations, or implement unique mod mechanics that require runtime adjustments.

## Core Concepts

### Targeting Entities

The ConfigGun targets entities based on their type or specific properties. This allows for precise application of modifications.

### Configuration Properties

The ConfigGun can modify a wide range of properties associated with entities. These properties are often represented as key-value pairs.

## Using the ConfigGun

The ConfigGun is typically activated and used within the game. Its interface and functionality are designed for in-game interaction.

### Basic Usage

1.  **Equip the ConfigGun:** The ConfigGun needs to be in the player's inventory and equipped.
2.  **Target an Entity:** Aim the ConfigGun at the desired entity.
3.  **Apply Modifications:** Use the ConfigGun's interface to select and modify properties.

### Advanced Usage

Advanced usage involves understanding the specific properties that can be modified and how they affect game behavior. This often requires knowledge of Noita's internal entity structure and scripting.

## Configurable Properties

The ConfigGun can modify numerous properties. The exact list and their effects can be extensive and may vary with game updates. Below are some common categories and examples.

### Entity Components

Entities in Noita are composed of various components, each responsible for a specific behavior or attribute. The ConfigGun can often modify parameters within these components.

#### Example: `DamageModelComponent`

This component governs how an entity deals damage.

| Property        | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `damage`        | The base damage value.                                                   |
| `damage_type`   | The type of damage (e.g., `damage_type_physical`, `damage_type_fire`). |
| `knockback`     | The force of knockback applied.                                          |
| `hit_particles` | The particle effect spawned on hit.                                      |

#### Example: `HealthComponent`

This component manages an entity's health.

| Property      | Description                               |
| :------------ | :---------------------------------------- |
| `max_hp`      | The maximum health points.                |
| `current_hp`  | The current health points.                |
| `invincible`  | Whether the entity is invincible.         |
| `healing_rate`| The rate at which the entity heals.       |

### Spell Properties

When applied to spell entities or entities that spawn spells, the ConfigGun can alter spell behavior.

#### Example: Spell Properties

| Property             | Description