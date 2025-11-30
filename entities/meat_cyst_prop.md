---
title: Meat Cyst Prop
category: entities
---

# Meat Cyst Prop

This document describes the `meat_cyst.xml` entity, a prop found in Noita. It's a hittable object that reacts to damage by potentially exploding and spawning projectiles.

## Key Components and Attributes

### Entity Tags

*   `hittable`: Indicates the entity can be targeted and damaged.
*   `prop`: Classifies the entity as a prop within the game world.

### HitboxComponent

Defines the physical boundaries of the entity for collision detection.

*   `aabb_min_x`: Minimum X-axis coordinate of the bounding box.
*   `aabb_max_x`: Maximum X-axis coordinate of the bounding box.
*   `aabb_min_y`: Minimum Y-axis coordinate of the bounding box.
*   `aabb_max_y`: Maximum Y-axis coordinate of the bounding box.

### LightComponent

Adds a light source to the entity.

*   `_enabled`: Controls whether the light is active (1 for enabled, 0 for disabled).
*   `radius`: The range of the light.
*   `r`, `g`, `b`: RGB color values for the light.
*   `fade_out_time`: Duration for the light to fade out.
*   `offset_y`: Vertical offset of the light source.

### DamageModelComponent

Manages how the entity takes damage and its material properties.

*   `air_needed`: Whether air is required for damage to be applied (0 means no air needed).
*   `falling_damages`: If the entity takes damage from falling.
*   `fire_damage_amount`: The amount of fire damage it can take.
*   `fire_probability_of_ignition`: The chance of igniting when exposed to fire.
*   `hp`: The entity's health points.
*   `materials_damage`: If the entity takes damage from specific materials.
*   `materials_that_damage`: A comma-separated list of materials that damage this entity (e.g., "acid,lava").
*   `materials_how_much_damage`: How much damage is dealt by the specified materials.
*   `blood_material`: The material that replaces the entity's "blood" when damaged.
*   `blood_multiplier`: Affects the amount of blood material created.
*   `physics_objects_damage`: If the entity takes damage from physics objects.
*   `create_ragdoll`: Whether a ragdoll is created upon death.

### ExplodeOnDamageComponent

Handles the entity's explosion behavior when damaged.

*   `explode_on_death_percent`: The percentage of HP remaining when the entity explodes upon death.
*   `explode_on_damage_percent`: The percentage of HP remaining when the entity explodes from taking damage.

#### config\_explosion

Configuration for the explosion effect.

*   `never_cache`: If set to 1, the explosion will not be cached.
*   `damage`: The damage dealt by the explosion.
*   `camera_shake`: The intensity of camera shake caused by the explosion.
*   `explosion_radius`: The radius of the explosion effect.
*   `explosion_sprite`: Path to the sprite used for the explosion visual.
*   `explosion_sprite_lifetime`: How long the explosion sprite lasts.
*   `load_this_entity`: Path to an entity to spawn upon explosion (e.g., a projectile).
*   `create_cell_probability`: Chance to create cells (particles) from the explosion.
*   `create_cell_cell_material`: The material of the cells created.
*   `hole_destroy_liquid`: If the explosion destroys liquids.
*   `hole_enabled`: If the explosion creates holes in the environment.
*   `ray_energy`: Energy of rays emitted by the explosion.
*   `particle_effect`: If particle effects are enabled for the explosion.
*   `damage_mortals`: If the explosion damages living entities.
*   `physics_throw_enabled`: If the explosion throws physics objects.
*   `shake_vegetation`: If the explosion shakes vegetation.
*   `sparks_count_max`, `sparks_count_min`: The range for the number of sparks created.
*   `sparks_enabled`: If sparks are enabled.
*   `stains_enabled`: If stains are created by the explosion.
*   `stains_radius`: The radius of the stains.
*   `audio_enabled`: If audio effects are enabled for the explosion.
*   `audio_event_name`: The name of the audio event to play.

### SpriteComponent

Defines the visual appearance of the entity.

*   `image_file`: Path to the sprite's image file.
*   `z_index`: Controls the rendering order of the sprite.

### LuaComponent

Attaches a Lua script to the entity for custom behavior.

*   `script_source_file`: Path to the Lua script file.
*   `execute_on_added`: If the script should run when the entity is added to the game.
*   `remove_after_executed`: If the Lua component should be removed after its initial execution.