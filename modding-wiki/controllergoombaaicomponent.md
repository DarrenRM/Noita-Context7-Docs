---
title: ControllerGoombaAIComponent
source: https://noita.wiki.gg/wiki/Documentation:ControllerGoombaAIComponent
category: modding-wiki
---

# ControllerGoombaAIComponent

This documentation page details the `ControllerGoombaAIComponent` in Noita, a crucial component for defining the behavior of "Goomba" enemies. Understanding this component is essential for modders looking to customize enemy movement, pathfinding, and interaction within the game.

## Overview

The `ControllerGoombaAIComponent` is responsible for the AI logic of enemies that exhibit "Goomba-like" behavior. This typically involves simple, direct movement patterns, often with a focus on approaching the player or following predefined paths. Modders can leverage this component to alter how these enemies perceive their environment, react to threats, and navigate the game world.

## Component Properties

The `ControllerGoombaAIComponent` has several properties that can be modified to influence its behavior. These properties are typically defined within an entity's XML definition.

### `speed`

*   **Type:** `float`
*   **Description:** Determines the movement speed of the Goomba AI. A higher value results in faster movement.

### `acceleration`

*   **Type:** `float`
*   **Description:** Controls how quickly the AI reaches its maximum `speed`. A higher value means faster acceleration.

### `friction`

*   **Type:** `float`
*   **Description:** Represents the deceleration applied to the AI when it's not actively moving. This affects how quickly it stops.

### `jump_force`

*   **Type:** `float`
*   **Description:** The vertical force applied when the AI attempts to jump. This is used for overcoming small obstacles or navigating uneven terrain.

### `jump_duration`

*   **Type:** `float`
*   **Description:** The duration for which the jump force is applied.

### `jump_cooldown`

*   **Type:** `float`
*   **Description:** The time in seconds that must pass before the AI can jump again.

### `detection_radius`

*   **Type:** `float`
*   **Description:** The radius around the AI within which it can detect the player or other targets.

### `detection_angle`

*   **Type:** `float`
*   **Description:** The field of view angle (in degrees) for detecting targets. A smaller angle means a narrower cone of vision.

### `target_detection_offset_y`

*   **Type:** `float`
*   **Description:** An offset applied to the Y-axis when checking for target detection, allowing for more precise targeting.

### `pathfinding_enabled`

*   **Type:** `bool`
*   **Description:** If `true`, the AI will attempt to use pathfinding to reach its target. If `false`, it will use simpler direct movement.

### `pathfinding_max_distance`

*   **Type:** `float`
*   **Description:** The maximum distance the AI will attempt to pathfind. Beyond this distance, it might revert to simpler movement or stop.

### `pathfinding_step_size`

*   **Type:** `float`
*   **Description:** The granularity of the pathfinding grid. Smaller values lead to more precise pathfinding but can be more computationally intensive.

### `pathfinding_smoothness`

*   **Type:** `float`
*   **Description:** Controls how smooth the generated paths are. Higher values result in smoother, less jagged paths.

### `pathfinding_avoid_obstacles`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will actively try to avoid obstacles.

### `pathfinding_avoid_player`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid the player, which can be useful for certain enemy behaviors.

### `pathfinding_avoid_enemies`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid other enemies.

### `pathfinding_avoid_projectiles`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid projectiles.

### `pathfinding_avoid_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid liquids.

### `pathfinding_avoid_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid solid terrain.

### `pathfinding_avoid_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid walls.

### `pathfinding_avoid_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid the ground, potentially leading to flying or hovering behavior.

### `pathfinding_avoid_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid empty air, encouraging the AI to stay grounded.

### `pathfinding_avoid_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid water.

### `pathfinding_avoid_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid lava.

### `pathfinding_avoid_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid acid.

### `pathfinding_avoid_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid poison.

### `pathfinding_avoid_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid magic effects.

### `pathfinding_avoid_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid fire.

### `pathfinding_avoid_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid electricity.

### `pathfinding_avoid_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid ice.

### `pathfinding_avoid_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid oil.

### `pathfinding_avoid_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid blood.

### `pathfinding_avoid_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid slime.

### `pathfinding_avoid_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid fungus.

### `pathfinding_avoid_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid gas.

### `pathfinding_avoid_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid explosions.

### `pathfinding_avoid_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that deal damage.

### `pathfinding_avoid_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that heal.

### `pathfinding_avoid_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that apply status effects.

### `pathfinding_avoid_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that apply buffs.

### `pathfinding_avoid_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that apply debuffs.

### `pathfinding_avoid_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that deal friendly fire damage.

### `pathfinding_avoid_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that deal enemy fire damage.

### `pathfinding_avoid_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid areas that deal player fire damage.

### `pathfinding_avoid_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of damage.

### `pathfinding_avoid_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of healing.

### `pathfinding_avoid_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of status effects.

### `pathfinding_avoid_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of buffs.

### `pathfinding_avoid_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of debuffs.

### `pathfinding_avoid_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of friendly fire damage.

### `pathfinding_avoid_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of enemy fire damage.

### `pathfinding_avoid_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all sources of player fire damage.

### `pathfinding_avoid_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all damage.

### `pathfinding_avoid_all_types_except_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all healing.

### `pathfinding_avoid_all_types_except_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all status effects.

### `pathfinding_avoid_all_types_except_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all buffs.

### `pathfinding_avoid_all_types_except_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all debuffs.

### `pathfinding_avoid_all_types_except_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all friendly fire.

### `pathfinding_avoid_all_types_except_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all enemy fire.

### `pathfinding_avoid_all_types_except_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all player fire.

### `pathfinding_avoid_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for all player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for debuffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_friendly_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for friendly fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_enemy_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for enemy fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_player_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for player fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ground`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for the ground.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_air`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for air.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_walls`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for walls.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_liquids`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for liquids.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_terrain`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for terrain.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_water`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for water.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_lava`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for lava.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_acid`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for acid.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_poison`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for poison.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_magic`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for magic.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fire`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fire.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_electricity`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for electricity.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_ice`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for ice.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_oil`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for oil.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_blood`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for blood.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_slime`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for slime.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_fungus`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for fungus.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_gas`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for gas.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_explosions`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for explosions.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for damage.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_healing`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for healing.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_status_effects`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for status effects.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_buffs`

*   **Type:** `bool`
*   **Description:** If `true`, the pathfinding algorithm will attempt to avoid all types of terrain and effects except for buffs.

### `pathfinding_avoid_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_all_types_except_debuffs`