---
title: Candle Prop
category: entities
---

# Candle Prop

This document describes the `candle_3.xml` entity, a prop representing a candle in Noita. It details its physical properties, visual representation, and interactive elements.

## Key Components

### HitboxComponent
Defines the collision area of the candle.

*   `aabb_min_x`: -1
*   `aabb_max_x`: 1
*   `aabb_min_y`: -4
*   `aabb_max_y`: 1

### VelocityComponent
Indicates that the entity can have velocity.

### SimplePhysicsComponent
Applies basic physics to the entity.

### LightComponent
Manages the light emitted by the candle.

*   `_enabled`: 1 (Enabled by default)
*   `radius`: 72 (The range of the light)
*   `fade_out_time`: 1.5 (How long it takes for the light to fade)
*   `offset_y`: -4 (Vertical offset of the light source)

### DamageModelComponent
Handles how the candle takes damage and its properties when damaged.

*   `air_needed`: 0 (Does not require air to function)
*   `blood_material`: "wax" (The material that bleeds when damaged)
*   `drop_items_on_death`: 0 (Does not drop items upon destruction)
*   `falling_damages`: 0 (Does not take damage from falling)
*   `fire_damage_amount`: 0.2 (Amount of damage taken from fire)
*   `fire_probability_of_ignition`: 0 (Cannot be ignited by fire)
*   `hp`: 0.1 (Very low health, easily destroyed)
*   `materials_damage`: 1 (Can be damaged by materials)
*   `ragdoll_material`: "wood_static" (Material used for its ragdoll if applicable)

### SpriteComponent (Primary)
Defines the main visual sprite for the candle.

*   `image_file`: "data/props_gfx/candle_3.xml" (Path to the sprite image)
*   `offset_x`: 0
*   `offset_y`: 0

### Base (Inheritance)
Inherits properties and components from `base_torch_particle.xml`. This likely includes particle effects associated with torches.

#### ParticleEmitterComponent (within Base)
Responsible for emitting particles, likely for flame effects.

*   `offset.y`: -4
*   `x_pos_offset_min`: -2
*   `x_pos_offset_max`: 1
*   `count_min`: 2
*   `count_max`: 2

*   `offset.y`: -4
*   `x_pos_offset_min`: -2
*   `x_pos_offset_max`: 1
*   `count_min`: 1
*   `count_max`: 1

### SpriteComponent (Emissive)
Defines an emissive sprite, likely for the glowing part of the flame.

*   `image_file`: "data/props_gfx/candle_3_emissive.xml" (Path to the emissive sprite image)
*   `emissive`: 1 (Marks this sprite as emissive)
*   `additive`: 1 (Uses additive blending for the glow effect)
*   `rect_animation`: "stand" (Specifies a standing animation)

### TorchComponent
Indicates that this entity functions as a torch.

*   `_tags`: "enabled_in_world" (Component is active when in the game world)

### SpriteAnimatorComponent
Handles sprite animations for the entity.