---
title: Scavenger Mine Projectile
category: entities
---

# Scavenger Mine Projectile

This document details the configuration for the Scavenger Mine projectile entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Entity Properties

The base entity defines fundamental behaviors and interactions.

*   **`name`**: `$projectile_default` - A generic projectile identifier.
*   **`tags`**: `hittable,teleportable_NOT` - Indicates the mine can be hit and is not affected by teleportation.

## Damage Component

Manages the mine's health and how it reacts to damage.

*   **`hp`**: `0.5` - The mine's health points.
*   **`materials_create_messages`**: `1` - Enables the creation of messages when materials interact with the mine.
*   **`ragdoll_material`**: `metal_rust` - Specifies the material for the ragdoll effect upon destruction.

## Hitbox Component

Defines the physical boundaries of the mine for collision detection.

*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: `"-3"` to `"3"` - Sets a small bounding box for the mine.
*   **`is_enemy`**: `1` - Marks the mine as an enemy.
*   **`is_item`**: `0` - Indicates it's not an item.
*   **`is_player`**: `0` - Indicates it's not the player.

## Crawler Animal Component

This component, despite its name, seems to influence the mine's movement and interaction with surfaces.

*   **`gravity`**: `600` - The gravitational pull affecting the mine.
*   **`speed`**: `0` - The mine does not move on its own.
*   **`collision_damage`**: `0` - The mine does not deal damage on simple collision.

## Collision Trigger Component

Defines an area that triggers an event when a specific entity tag enters it.

*   **`width`, `height`, `radius`**: `40`, `40`, `20` - Sets the trigger area dimensions.
*   **`required_tag`**: `"mortal"` - The trigger activates when an entity with the "mortal" tag enters the area.
*   **`timer_for_destruction`**: `30` - The mine is destroyed after 30 frames when the trigger condition is met.

## Lua Components

These components execute custom scripts for specific events.

*   **`script_collision_trigger_hit`**: `"data/scripts/projectiles/mine_animate.lua"` - This script is executed when the `CollisionTriggerComponent` is activated.
*   **`script_damage_received`**: `"data/scripts/projectiles/mine_animate.lua"` - This script is executed when the mine receives damage.
*   **`remove_after_executed`**: `1` - The Lua component is removed after its script has executed.

## Sprite Components

Defines the visual appearance of the mine.

*   **`image_file`**: `"data/enemies_gfx/mine.xml"` - The primary sprite for the mine.
*   **`rect_animation`**: `"stand"` - Specifies the animation state.
*   **`image_file`** (emissive): `"data/enemies_gfx/mine_emissive.xml"` - An additional emissive sprite for visual effects.
*   **`emissive`**: `1` - Enables emissive properties for the sprite.
*   **`additive`**: `1` - Uses additive blending for the emissive sprite.

## Move To Surface On Create Component

Ensures the mine is positioned on a surface when it's created.

*   **`offset_from_surface`**: `0` - No offset from the surface.

## Camera Bound Component

Controls how the camera behaves relative to the mine.

*   **`distance`**: `160000` - The maximum distance the mine can be from the camera before it's potentially culled.

## Explosion Component

Defines the explosion effect that occurs when the mine is destroyed.

*   **`trigger`**: `"ON_DEATH"` - The explosion occurs when the mine dies.
*   **`config_explosion`**: Contains detailed parameters for the explosion:
    *   **`camera_shake`**: `25.0` - The intensity of camera shake.
    *   **`explosion_radius`**: `30` - The radius of the explosion.
    *   **`explosion_sprite`**: `"data/particles/explosion_040_poof.xml"` - The visual sprite for the explosion.
    *   **`load_this_entity`**: `"data/entities/particles/particle_explosion/main_gunpowder_small.xml"` - An entity to load for the explosion effect.
    *   **`create_cell_probability`**: `80` - Probability of creating cells.
    *   **`create_cell_material`**: `"fire"` - The material of the created cells.
    *   **`ray_energy`**: `170000` - The energy of the explosion's rays.
    *   **`damage`**: `4` - The damage dealt by the explosion.
    *   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
    *   **`damage_mortals`**: `1` - The explosion damages mortal entities.
    *   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `2.3` to `3.6` - The range of physics force applied by the explosion.
    *   **`sparks_enabled`**: `1` - Enables sparks.
    *   **`stains_enabled`**: `1` - Enables explosion stains on surfaces.