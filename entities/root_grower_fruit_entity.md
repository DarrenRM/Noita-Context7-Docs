---
title: Root Grower Fruit Entity
category: entities
---

# Root Grower Fruit Entity

This document describes the `root_grower_fruit.xml` entity, a prop found in Noita. It details its physical properties, damage interactions, and explosive behavior when damaged.

## Key Components and Attributes

### Entity Tags
- `hittable`: Indicates the entity can be targeted and damaged.
- `prop`: Classifies the entity as a prop within the game world.

### HitboxComponent
Defines the collision boundaries of the entity.
- `aabb_min_x`: -6
- `aabb_max_x`: 6
- `aabb_min_y`: -10
- `aabb_max_y`: 4

### LightComponent
Adds a light source to the entity.
- `_enabled`: 1 (enabled)
- `radius`: 100
- `r`: 255 (Red component of the light color)
- `g`: 20 (Green component of the light color)
- `b`: 255 (Blue component of the light color)
- `fade_out_time`: 1.5 (Seconds for the light to fade out)
- `offset_y`: -6 (Vertical offset of the light source)

### DamageModelComponent
Governs how the entity reacts to damage and environmental effects.
- `air_needed`: 0 (Does not require air to function)
- `falling_damages`: 1 (Takes damage from falling)
- `fire_damage_amount`: 0.5 (Amount of fire damage taken)
- `fire_probability_of_ignition`: 0.8 (Probability of igniting from fire)
- `hp`: 1 (Hit points of the entity)
- `materials_damage`: 1 (Can be damaged by materials)
- `materials_that_damage`: `acid,lava` (Materials that can damage this entity)
- `materials_how_much_damage`: `0.004,0.004` (Damage amount from specified materials)
- `blood_material`: `grass` (Material produced when damaged)
- `blood_multiplier`: 0.3 (Multiplier for blood generation)
- `physics_objects_damage`: 1 (Can be damaged by physics objects)
- `create_ragdoll`: 0 (Does not create a ragdoll upon death)

### ExplodeOnDamageComponent
Defines the entity's explosive behavior when damaged.
- `explode_on_death_percent`: 1 (Always explodes upon death)
- `explode_on_damage_percent`: 0.2 (Explodes when reaching 20% of its health)

#### config_explosion
Configuration for the explosion effect.
- `never_cache`: 0 (Can be cached)
- `damage`: 1 (Damage dealt by the explosion)
- `camera_shake`: 2 (Intensity of camera shake)
- `explosion_radius`: 12 (Radius of the explosion)
- `explosion_sprite`: `data/particles/explosion_016.xml` (Sprite used for the explosion effect)
- `explosion_sprite_lifetime`: 10 (Duration the explosion sprite is visible)
- `load_this_entity`: `data/entities/projectiles/gasblob.xml` (Entity to spawn upon explosion)
- `create_cell_probability`: 80 (Probability of creating cells)
- `hole_destroy_liquid`: 0 (Does not destroy liquids)
- `hole_enabled`: 1 (Enables hole creation)
- `ray_energy`: 10000 (Energy of rays emitted by the explosion)
- `particle_effect`: 1 (Enables particle effects)
- `damage_mortals`: 1 (Deals damage to mortals)
- `physics_throw_enabled`: 0 (Does not throw physics objects)
- `shake_vegetation`: 1 (Shakes vegetation)
- `sparks_count_max`: 30 (Maximum number of sparks)
- `sparks_count_min`: 15 (Minimum number of sparks)
- `sparks_enabled`: 1 (Enables sparks)
- `stains_enabled`: 1 (Enables stains)
- `stains_radius`: 10 (Radius of stains)
- `audio_enabled`: 1 (Enables audio effects)
- `audio_event_name`: `explosions/slime` (Name of the audio event for the explosion)

### SpriteComponent
Defines the visual representation of the entity.
- `image_file`: `data/props_gfx/root_grower_fruit.xml` (Path to the sprite's XML definition)
- `z_index`: -0.5 (Layering of the sprite, lower values are further back)