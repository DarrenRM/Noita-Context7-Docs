---
title: Wisp Entity
category: entities
---

# Wisp Entity

This document details the configuration of the Wisp entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Attributes

The Wisp is a spectral entity with unique properties, primarily designed to inflict a curse upon players.

### Entity Tags

These tags define the fundamental behavior and interactions of the Wisp.

*   `hittable`: The entity can be damaged.
*   `islandspirit`: Identifies it as a spirit associated with the island biome.
*   `necrobot_NOT`: Excludes it from certain behaviors related to NecroBots.
*   `glue_NOT`: Prevents it from being affected by glue.
*   `curse_NOT`: Prevents it from being affected by curses.

### Physics Component (`SimplePhysicsComponent`)

Enables basic physics interactions for the entity.

*   `_tags="enabled_in_world"`: The component is active when the entity is in the game world.

### Hitbox Component (`HitboxComponent`)

Defines the collision area of the Wisp.

*   `aabb_min_x="-4"`: Minimum X-axis bounding box coordinate.
*   `aabb_max_x="4"`: Maximum X-axis bounding box coordinate.
*   `aabb_min_y="-4"`: Minimum Y-axis bounding box coordinate.
*   `aabb_max_y="4"`: Maximum Y-axis bounding box coordinate.

### Damage Component (`DamageModelComponent`)

Manages the Wisp's health and how it takes damage.

*   `hp="20"`: The Wisp has 20 hit points.
*   `air_needed="0"`: Does not require air to survive.
*   `falling_damages="0"`: Does not take damage from falling.
*   `fire_damage_amount="0.1"`: Small amount of damage from fire.
*   `fire_probability_of_ignition="0"`: Cannot be set on fire.
*   `blood_material="plasma_fading"`: The material of its "blood" effect.
*   `blood_spray_material="plasma_fading"`: The material of its "blood spray" effect.
*   `materials_damage="1"`: Can be damaged by certain materials.
*   `materials_how_much_damage="0.1"`: The amount of damage taken from those materials.
*   `materials_that_damage="acid"`: Specifically damaged by acid.
*   `ragdoll_fx_forced="DISINTEGRATED"`: The visual effect when it disintegrates.
*   `ragdoll_material="spark_blue"`: The material used for its disintegration sparks.

#### Damage Multipliers

These multipliers determine how much damage the Wisp takes from different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.0`      |
| `projectile`| `0.0`      |
| `explosion` | `0.0`      |
| `electricity`| `0.0`      |
| `fire`      | `0.0`      |
| `slice`     | `0.0`      |
| `ice`       | `0.0`      |
| `holy`      | `0.0`      |

### Area Damage Component (`AreaDamageComponent`)

Defines an area around the Wisp that damages entities within it.

*   `aabb_min.x="-16"`: Minimum X-axis of the damage area.
*   `aabb_min.y="-16"`: Minimum Y-axis of the damage area.
*   `aabb_max.x="16"`: Maximum X-axis of the damage area.
*   `aabb_max.y="16"`: Maximum Y-axis of the damage area.
*   `damage_per_frame="0.3"`: Deals 0.3 damage per frame to entities within the area.
*   `update_every_n_frame="1"`: The damage is applied every frame.
*   `entities_with_tag="player_unit"`: Only affects entities tagged as `player_unit`.
*   `death_cause="$damage_rock_curse"`: The cause of death for entities killed by this area damage.
*   `damage_type="DAMAGE_HOLY"`: The type of damage dealt.
*   `circle_radius="16"`: The radius of the circular damage area.

### Velocity Component (`VelocityComponent`)

Controls the movement and gravity of the Wisp.

*   `_tags="enabled_in_world"`: The component is active when the entity is in the game world.
*   `gravity_y="0"`: The Wisp is not affected by gravity.

### Sprite Component (`SpriteComponent`)

Defines the visual appearance of the Wisp.

*   `image_file="data/projectiles_gfx/death_ghost.xml"`: Uses the `death_ghost` sprite.
*   `emissive="1"`: The sprite emits light.
*   `additive="1"`: The sprite uses additive blending for its rendering.

### Lua Component (`LuaComponent`)

Attaches a Lua script to control the Wisp's behavior.

*   `script_source_file="data/entities/animals/boss_spirit/wisp_move.lua"`: The script responsible for the Wisp's movement and AI.
*   `execute_every_n_frame="1"`: The script's logic is executed every frame.