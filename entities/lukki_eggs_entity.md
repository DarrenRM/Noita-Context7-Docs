---
title: Lukki Eggs Entity
category: entities
---

# Lukki Eggs Entity

This document describes the `lukki_eggs.xml` entity, which represents the eggs laid by Lukki enemies in Noita. This entity is designed to be a destructible object that can spill its contents when damaged.

## Key Components and Attributes

The `lukki_eggs.xml` entity is composed of several components that define its behavior and appearance.

### Entity Tags

*   `mortal`: This tag is crucial as it allows the entity to be destroyed and trigger death-related events, such as explosions or material spills.
*   `hittable`: Indicates that the entity can be targeted and damaged by player actions or environmental effects.
*   `glue_NOT`: This tag suggests that the entity is not affected by glue in a way that would prevent its destruction or interaction.

### SpriteComponent

This component defines the visual representation of the Lukki Eggs.

*   `image_file`: Specifies the path to the sprite's graphical asset (`data/buildings_gfx/lukki_eggs.xml`).
*   `offset_x`, `offset_y`: Define the sprite's position relative to the entity's origin.

### LightComponent

This component adds a light source to the entity.

*   `_enabled`: Set to `1` to activate the light.
*   `radius`: Determines the range of the light emitted by the eggs.

### HitboxComponent

Defines the collision area of the Lukki Eggs.

*   `aabb_min_x`, `aabb_max_x`: Set the bounding box's minimum and maximum X-coordinates.
*   `aabb_min_y`, `aabb_max_y`: Set the bounding box's minimum and maximum Y-coordinates.

### DamageModelComponent

Manages how the entity takes damage and its properties related to destruction.

*   `hp`: The health points of the Lukki Eggs.
*   `fire_damage_amount`: The amount of damage taken from fire.
*   `critical_damage_resistance`: Resistance to critical hits.
*   `blood_material`: The material that spills when the entity is damaged (set to `slime`).
*   `ragdoll_material`: The material used for its ragdoll if applicable.

### CameraBoundComponent

Controls how the entity behaves in relation to the camera.

*   `max_count`: The maximum number of these entities that can exist simultaneously.
*   `distance`: The distance from the camera within which the entity is considered active.

### MaterialInventoryComponent

Manages the materials contained within the Lukki Eggs.

*   `on_death_spill`: Set to `1` to ensure materials are spilled upon death.
*   `leak_on_damage_percent`: The percentage of damage at which the entity starts leaking its materials.
*   `count_per_material_type`: Defines the types and amounts of materials stored.
    *   `Material material="slime" count="50"`: The eggs contain 50 units of `slime`.

### LuaComponent

Links the entity to a Lua script for custom behavior.

*   `script_damage_received`: Specifies the Lua script to execute when the entity receives damage (`data/scripts/buildings/lukki_eggs.lua`).