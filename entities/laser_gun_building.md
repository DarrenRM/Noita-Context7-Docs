---
title: Laser Gun Building
category: entities
---

# Laser Gun Building

This document details the configuration of the Laser Gun building entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Entity Properties

The `Entity` tag defines the fundamental properties of the Laser Gun.

*   **Tags**: `mortal`, `hittable`, `homing_target`, `glue_NOT`. These tags influence how the game interacts with the entity, such as its ability to be damaged, targeted, or affected by glue.

## DamageModelComponent

This component governs the health and damage resistance of the Laser Gun.

*   **hp**: `6.5` - The total health points of the Laser Gun.
*   **ragdoll_material**: `steel` - The material used for the ragdoll effect when destroyed.
*   **blood_material**: `copper` - The material associated with blood effects.
*   **fire_probability_of_ignition**: `0` - The probability of igniting from fire.
*   **air_needed**: `0` - Indicates if air is required for its function (0 means no).

### Damage Multipliers

These multipliers determine how much damage the Laser Gun takes from different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `drill`     | `0.1`      |
| `projectile`| `0.1`      |
| `fire`      | `0.0`      |
| `ice`       | `0.2`      |
| `slice`     | `0.0`      |

## SpriteComponent

Defines the visual representation of the Laser Gun.

*   **image\_file**: `data/buildings_gfx/lasergun.xml` - Path to the sprite definition file.
*   **special\_scale\_x**: `1`
*   **has\_special\_scale**: `1`
*   **offset\_x**: `0`
*   **offset\_y**: `0`

## SpriteAnimatorComponent

This component handles sprite animations. It is present but has no specific configurable attributes listed in this snippet.

## HitboxComponent

Defines the collision area of the Laser Gun.

*   **aabb\_min\_x**: `-5`
*   **aabb\_max\_x**: `4`
*   **aabb\_min\_y**: `-5`
*   **aabb\_max\_y**: `5`

## CameraBoundComponent

Controls how the entity behaves relative to the camera.

*   **max\_count**: `30` - Maximum number of this entity that can be active within the camera's view.
*   **distance**: `160000` - The distance from the camera at which the entity is considered.

## VariableStorageComponent

Allows for storing and managing variables within the entity.

*   **name**: `timing`
*   **value\_int**: `-1`

## LuaComponent

This component enables custom scripting for the Laser Gun's behavior.

*   **script\_source\_file**: `data/scripts/buildings/lasergun.lua` - The Lua script file that controls its functionality.
*   **execute\_every\_n\_frame**: `10` - The script will execute every 10 frames.

## LightComponent

Adds a light source to the Laser Gun.

*   **radius**: `96` - The radius of the light.
*   **fade\_out\_time**: `1.5` - The time it takes for the light to fade out.
*   **r**: `230` - Red component of the light color.
*   **g**: `120` - Green component of the light color.
*   **b**: `230` - Blue component of the light color.