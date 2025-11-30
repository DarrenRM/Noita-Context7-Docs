---
title: Candle Prop Entity
category: entities
---

# Candle Prop Entity

This document details the `candle_2.xml` entity, which represents a basic candle prop in Noita. It's designed to be a simple, hittable object that emits light and can be ignited.

## Core Components

The `candle_2.xml` entity is built using several key components that define its behavior and appearance.

### Entity Tags

*   `hittable`: Indicates that the entity can be interacted with by projectiles or other damage sources.
*   `prop`: Classifies the entity as a decorative or functional prop within the game world.

### HitboxComponent

Defines the physical boundaries of the candle for collision detection.

*   `aabb_min_x`: -1
*   `aabb_max_x`: 1
*   `aabb_min_y`: -5
*   `aabb_max_y`: 1

### VelocityComponent

Allows the entity to have velocity, though it's not actively used for movement in this static prop.

### SimplePhysicsComponent

Enables basic physics interactions, such as gravity and collision response.

### LightComponent

Manages the light emitted by the candle.

*   `_enabled`: 1 (The light is active by default)
*   `radius`: 56 (The range of the light)
*   `fade_out_time`: 1.5 (How long the light takes to fade)
*   `offset_y`: -8 (Vertical offset of the light source)

### DamageModelComponent

Handles how the candle reacts to damage and its own health.

*   `air_needed`: 0 (Does not require air to function)
*   `blood_material`: wax (The material that drips when damaged, simulating wax)
*   `drop_items_on_death`: 0 (Does not drop items when destroyed)
*   `falling_damages`: 0 (Does not take damage from falling)
*   `fire_damage_amount`: 0.2 (The amount of damage taken from fire per tick)
*   `fire_probability_of_ignition`: 0 (Cannot be ignited by fire itself)
*   `critical_damage_resistance`: 1 (Has full resistance to critical damage)
*   `hp`: 0.1 (Very low health, easily destroyed)
*   `is_on_fire`: 0 (Not on fire by default)
*   `materials_create_messages`: 0 (Does not generate messages when materials interact)
*   `materials_damage`: 1 (Takes damage from certain materials)
*   `ragdoll_filenames_file`: "" (No specific ragdoll files)
*   `ragdoll_material`: wood_static (The material used for its static ragdoll if it were to ragdoll)
*   `ui_report_damage`: 0 (Does not report damage to the UI)

### SpriteComponent (Primary)

Defines the main visual representation of the candle.

*   `_tags`: "character" (This tag is unusual for a prop and might be a remnant or intended for specific interactions)
*   `image_file`: `data/props_gfx/candle_2.xml` (Path to the sprite's graphical data)
*   `offset_x`: 0
*   `offset_y`: 0

### Base (Inheritance)

The entity inherits properties from `data/entities/base_torch_particle.xml`. This is crucial for its particle effects.

#### ParticleEmitterComponent (within Base)

These components are responsible for the flame particles.

*   `offset.y`: -8 (Vertical offset for particle emission)
*   `x_pos_offset_min`: -2
*   `x_pos_offset_max`: 1
*   `count_min`: 1
*   `count_max`: 1 (Emits a small, consistent number of particles)

### SpriteComponent (Emissive)

This component adds an emissive glow to the candle, enhancing its light effect.

*   `_tags`: "character" (Again, an unusual tag for a prop)
*   `alpha`: 1 (Fully opaque)
*   `image_file`: `data/props_gfx/candle_2_emissive.xml` (Path to the emissive sprite data)
*   `offset_x`: 0
*   `offset_y`: 0
*   `emissive`: 1 (Enables emissive properties)
*   `additive`: 1 (Adds the emissive color to the scene)
*   `rect_animation`: "stand" (Specifies the animation state)

### TorchComponent

This component likely enables the candle to function as a light source and potentially interact with other torch-related mechanics.

*   `_tags`: "enabled_in_world" (The torch functionality is active when in the game world)

### SpriteAnimatorComponent

Allows for sprite animations, though the specific animations are defined in the `SpriteComponent`'s `rect_animation` and `next_rect_animation` attributes.

## Summary

The `candle_2.xml` entity is a straightforward prop designed to add ambient light and a visual element to the game. Its primary functions are to emit light via the `LightComponent` and display its visual form through `SpriteComponent`s. The inheritance from `base_torch_particle.xml` ensures it has a flame effect. While it has a `DamageModelComponent`, its low HP and lack of ignition probability make it more of a destructible light source than a combat-oriented object. The repeated `_tags="character"` on its sprite components is noteworthy and might indicate a specific, albeit unusual, design choice for how it's intended to be processed by the game engine.