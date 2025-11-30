---
title: VerletWeaponComponent
source: https://noita.wiki.gg/wiki/Documentation:VerletWeaponComponent
category: modding-wiki
---

# VerletWeaponComponent

This documentation covers the `VerletWeaponComponent` in Noita, a crucial component for creating projectile-based weapons with unique physics behaviors. Understanding this component is essential for modders looking to implement weapons that simulate chain reactions, fluid dynamics, or other complex projectile interactions.

## Overview

The `VerletWeaponComponent` is a powerful tool for creating weapons that don't just fire a single projectile. Instead, it allows for the creation of a "chain" of projectiles that interact with each other and the environment using Verlet integration, a numerical method for integrating Newton's equations of motion. This enables a wide range of effects, from whips and chains to fluid-like projectiles and complex particle systems.

## Component Properties

The `VerletWeaponComponent` has several properties that can be configured in your weapon's XML definition to control its behavior.

### Core Properties

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `num_particles` | int | The number of particles in the Verlet chain. | 10 |
| `particle_spacing` | float | The initial distance between particles in the chain. | 0.5 |
| `particle_mass` | float | The mass of each individual particle. | 1.0 |
| `particle_radius` | float | The radius of each particle, used for collision detection. | 0.1 |
| `gravity` | float | The gravitational force applied to each particle. | 1.0 |
| `drag` | float | Air resistance applied to each particle. | 0.05 |
| `stiffness` | float | Controls how much the particles resist stretching or compression. Higher values make the chain more rigid. | 100.0 |
| `damping` | float | Controls how quickly oscillations in the chain dissipate. Higher values reduce bouncing. | 10.0 |
| `collision_friction` | float | Friction applied when particles collide with the environment. | 0.2 |
| `collision_restitution` | float | Bounciness of particles upon collision. | 0.2 |
| `collision_group` | string | The collision group the particles belong to. | `PROJECTILE` |
| `collision_mask` | string | The collision mask, determining what the particles can collide with. | `ALL` |
| `damage_min` | float | The minimum damage dealt by each particle. | 1.0 |
| `damage_max` | float | The maximum damage dealt by each particle. | 5.0 |
| `damage_type` | string | The type of damage dealt (e.g., `PROJECTILE`, `PHYSICAL`). | `PROJECTILE` |
| `damage_probability` | float | The probability (0.0 to 1.0) that a particle will deal damage. | 1.0 |
| `damage_radius` | float | The radius around a particle that applies damage. | 0.2 |
| `damage_delay` | float | Delay in seconds before particles start dealing damage. | 0.0 |
| `damage_interval` | float | Time in seconds between damage ticks for a single particle. | 0.1 |
| `damage_effect_material` | string | The material to spawn when damage is dealt. | `damage_visual` |
| `damage_effect_radius` | float | The radius of the damage effect. | 0.2 |
| `damage_effect_spawn_probability` | float | Probability of spawning the damage effect. | 1.0 |
| `damage_effect_lifetime` | float | Lifetime of the damage effect. | 0.2 |
| `damage_effect_speed` | float | Speed of the damage effect. | 0.0 |
| `damage_effect_random_rotation` | bool | Whether to randomize the rotation of the damage effect. | `false` |
| `damage_effect_random_scale` | bool | Whether to randomize the scale of the damage effect. | `false` |
| `damage_effect_random_offset` | bool | Whether to randomize the offset of the damage effect. | `false` |
| `damage_effect_random_color` | bool | Whether to randomize the color of the damage effect. | `false` |
| `damage_effect_random_frame` | bool | Whether to randomize the frame of the damage effect. | `false` |
| `damage_effect_random_material` | bool | Whether to randomize the material of the damage effect. | `false` |
| `damage_effect_random_entity` | bool | Whether to randomize the entity of the damage effect. | `false` |
| `damage_effect_random_position` | bool | Whether to randomize the position of the damage effect. | `false` |
| `damage_effect_random_rotation_speed` | bool | Whether to randomize the rotation speed of the damage effect. | `false` |
| `damage_effect_random_scale_speed` | bool | Whether to randomize the scale speed of the damage effect. | `false` |
| `damage_effect_random_offset_speed` | bool | Whether to randomize the offset speed of the damage effect. | `false` |
| `damage_effect_random_color_speed` | bool | Whether to randomize the color speed of the damage effect. | `false` |
| `damage_effect_random_frame_speed` | bool | Whether to randomize the frame speed of the damage effect. | `false` |
| `damage_effect_random_material_speed` | bool | Whether to randomize the material speed of the damage effect. | `false` |
| `damage_effect_random_entity_speed` | bool | Whether to randomize the entity speed of the damage effect. | `false` |
| `damage_effect_random_position_speed` | bool | Whether to randomize the position speed of the damage effect. | `false` |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_min` | float | Minimum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_entity_speed_max` | float | Maximum random entity speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_min` | float | Minimum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_position_speed_max` | float | Maximum random position speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_min` | float | Minimum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_rotation_max` | float | Maximum random rotation for the damage effect. | 0.0 |
| `damage_effect_random_scale_min` | float | Minimum random scale for the damage effect. | 0.0 |
| `damage_effect_random_scale_max` | float | Maximum random scale for the damage effect. | 0.0 |
| `damage_effect_random_offset_min` | float | Minimum random offset for the damage effect. | 0.0 |
| `damage_effect_random_offset_max` | float | Maximum random offset for the damage effect. | 0.0 |
| `damage_effect_random_color_min` | float | Minimum random color for the damage effect. | 0.0 |
| `damage_effect_random_color_max` | float | Maximum random color for the damage effect. | 0.0 |
| `damage_effect_random_frame_min` | int | Minimum random frame for the damage effect. | 0 |
| `damage_effect_random_frame_max` | int | Maximum random frame for the damage effect. | 0 |
| `damage_effect_random_material_min` | string | Minimum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_material_max` | string | Maximum random material for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_min` | string | Minimum random entity for the damage effect. | `damage_visual` |
| `damage_effect_random_entity_max` | string | Maximum random entity for the damage effect. | `visual_damage` |
| `damage_effect_random_position_min` | float | Minimum random position for the damage effect. | 0.0 |
| `damage_effect_random_position_max` | float | Maximum random position for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_min` | float | Minimum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_rotation_speed_max` | float | Maximum random rotation speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_min` | float | Minimum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_scale_speed_max` | float | Maximum random scale speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_min` | float | Minimum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_offset_speed_max` | float | Maximum random offset speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_min` | float | Minimum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_color_speed_max` | float | Maximum random color speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_min` | float | Minimum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_frame_speed_max` | float | Maximum random frame speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_min` | float | Minimum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_material_speed_max` | float | Maximum random material speed for the damage effect. | 0.0 |
| `damage_effect_random_