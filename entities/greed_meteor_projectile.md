---
title: Greed Meteor Projectile
category: entities
---

# Greed Meteor Projectile

This document describes the `greed_meteor.xml` entity, which defines a projectile used in Noita, specifically associated with the "Greed Curse" and visually resembling a meteor.

## Core Functionality

The `greed_meteor.xml` entity defines a projectile with the following key behaviors:

*   **Projectile Type:** It's a player-fired projectile.
*   **Physics:** It has gravity applied, a moderate mass, and air friction.
*   **Impact Behavior:** It explodes on collision with anything, on low velocity, and when its lifetime expires. It also dies upon colliding with liquids.
*   **Damage:** It deals direct damage and has a specific damage type for fire.
*   **Visuals:** It uses a green meteor sprite and emits green sparks and fire particles upon impact.
*   **Audio:** It has distinct projectile and looping audio events.
*   **Scripting:** It's linked to a Lua script for custom logic.

## Key Components and Attributes

### Entity: `greed_meteor.xml`

This is the root entity definition.

*   **`name`**: `$projectile_default` (Inherited, indicates a default projectile type)
*   **`tags`**: `projectile_player` (Identifies it as a player projectile)

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This section inherits properties from a generic projectile.

*   **`VelocityComponent`**:
    *   `gravity_y`: `50` (Applies downward acceleration)
    *   `air_friction`: `0` (No air resistance)
    *   `mass`: `0.3` (Lightweight projectile)

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's behavior.

*   **`_enabled`**: `1` (Component is active)
*   **`lob_min` / `lob_max`**: `0.8` / `1.0` (Controls the arc of the projectile)
*   **`speed_min` / `speed_max`**: `300` / `400` (Initial velocity range)
*   **`die_on_low_velocity`**: `1` (Explodes if speed drops too low)
*   **`on_death_explode`**: `1` (Explodes when it dies for any reason)
*   **`on_lifetime_out_explode`**: `1` (Explodes when its lifetime ends)
*   **`explosion_dont_damage_shooter`**: `1` (The explosion does not harm the player who fired it)
*   **`damage`**: `5` (Base damage dealt by the projectile itself)
*   **`on_collision_die`**: `1` (Destroys the projectile upon collision)
*   **`die_on_liquid_collision`**: `1` (Destroys the projectile upon hitting liquids)
*   **`lifetime`**: `800` (Duration in frames before expiring)
*   **`knockback_force`**: `3.0` (Force applied to entities hit by the projectile)
*   **`physics_impulse_coeff`**: `9000` (Coefficient for physics impulse on impact)

#### `damage_by_type`

*   **`fire`**: `10.25` (Additional fire damage dealt)

#### `config_explosion`

Defines the properties of the explosion upon the projectile's death.

*   **`never_cache`**: `1` (Ensures the explosion is always generated fresh)
*   **`camera_shake`**: `20.5` (Intensity of camera shake on explosion)
*   **`explosion_radius`**: `45` (Area of effect for the explosion)
*   **`explosion_sprite`**: `data/particles/explosion_040_poof_green.xml` (Visual effect for the explosion)
*   **`create_cell_probability`**: `100` (Always creates material cells)
*   **`create_cell_material`**: `fire` (The material created is fire)
*   **`damage`**: `10` (Damage dealt by the explosion itself)
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_green.xml,data/entities/misc/loose_ground.xml` (Entities to spawn on explosion, including green particle effects and loose ground)
*   **`ray_energy`**: `7500000` (Energy value for ray interactions)
*   **`hole_enabled`**: `1` (Creates holes in terrain)
*   **`particle_effect`**: `1` (Enables particle effects for the explosion)
*   **`damage_mortals`**: `1` (Explosion damages living entities)
*   **`physics_explosion_power.min` / `max`**: `2` / `4` (Minimum and maximum physics force of the explosion)
*   **`shake_vegetation`**: `1` (Causes vegetation to shake)
*   **`sparks_enabled`**: `1` (Sparks are generated)
*   **`sparks_count_min` / `max`**: `50` / `100` (Number of sparks)
*   **`spark_material`**: `spark_green` (The material of the sparks)
*   **`stains_enabled`**: `1` (Creates impact stains)

### Sprite Component (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/projectiles_gfx/meteor_green.xml` (The sprite asset for the green meteor)
*   **`emissive`**: `1` (The sprite emits light)
*   **`additive`**: `1` (Uses additive blending for the sprite)
*   **`z_index`**: `-0.5` (Determines rendering order)

### Particle Emitter Components (`ParticleEmitterComponent`)

These components generate various particle effects.

*   **Smoke Emitter:**
    *   `emitted_material_name`: `smoke`
    *   `count_min`/`max`: `5`
    *   `lifetime_min`/`max`: `0.1` / `0.3`
*   **Fire Emitter (Impact):**
    *   `emitted_material_name`: `fire`
    *   `count_min`/`max`: `1`
    *   `lifetime_min`/`max`: `0.1` / `0.3`
*   **Fire Emitter (Delayed/Custom):**
    *   `emitted_material_name`: `fire`
    *   `custom_style`: `FIRE`
    *   `color`: `ff9ae74a`
    *   `count_min`/`max`: `6`
    *   `lifetime_min`/`max`: `1.1` / `2.8`
    *   `delay_frames`: `2`
*   **Green Spark Emitter (Continuous):**
    *   `emitted_material_name`: `spark_green`
    *   `count_min`/`max`: `40` / `100`
    *   `lifetime_min`/`max`: `0.2` / `0.4`
    *   `emit_cosmetic_particles`: `1` (Only cosmetic particles)
    *   `create_real_particles`: `0`
*   **Green Spark Emitter (Explosive):**
    *   `emitted_material_name`: `spark_green`
    *   `count_min`/`max`: `80` / `120`
    *   `lifetime_min`/`max`: `0.1` / `0.2`
    *   `emit_cosmetic_particles`: `1`
    *   `create_real_particles`: `0`
    *   `is_emitting`: `0` (Starts off, likely triggered by explosion)

### Sprite Particle Emitter Component (`SpriteParticleEmitterComponent`)

Emits sprite-based particles.

*   **`sprite_file`**: `data/particles/fire_large_green.xml` (Uses a large green fire sprite)
*   **`count_min`/`max`**: `3` / `5`
*   **`randomize_position`**: Controls spread of particles.
*   **`randomize_velocity`**: Controls initial velocity of particles.
*   **`gravity.y`**: `10` (Particles are affected by gravity)

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   **`radius`**: `150` (The radius of the light emitted)

### Audio Component (`AudioComponent`)

Handles sound effects for the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` (Audio bank file)
*   **`event_root`**: `player_projectiles/meteor` (Root event for projectile sounds)

### Audio Loop Component (`AudioLoopComponent`)

Plays a looping sound effect.

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_name`**: `player_projectiles/meteor/loop`
*   **`auto_play`**: `1` (Starts playing automatically)

### Variable Storage Component (`VariableStorageComponent`)

Stores variables for use by other components.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/meteor_green.xml` (Likely references its own deck definition)

### Lua Component (`LuaComponent`)

Integrates custom Lua scripting.

*   **`script_source_file`**: `data/scripts/magic/greed_curse/greed_meteor.lua` (The associated Lua script for custom logic)
*   **`execute_on_removed`**: `1` (Script executes when the entity is removed)

## AI Modding Considerations

*   **Projectile Behavior:** Modders can alter `speed_min`, `speed_max`, `gravity_y`, `lifetime`, and `damage` to change how the meteor flies and hits.
*   **Explosion Customization:** The `config_explosion` section offers extensive control over the impact effect, including radius, damage, camera shake, and spawned entities/particles.
*   **Visuals and Effects:** Modifying `image_file` in `SpriteComponent` or the `sprite_file` in `SpriteParticleEmitterComponent` can change the projectile's appearance. The various `ParticleEmitterComponent`s allow for fine-tuning of smoke, fire, and spark effects.
*   **Audio Integration:** The `AudioComponent` and `AudioLoopComponent` can be pointed to different sound events for unique audio feedback.
*   **Scripting Logic:** The `LuaComponent` is the entry point for advanced AI-driven behaviors, allowing for custom effects, interactions, or even unique targeting logic. Modders can extend or replace the functionality defined in `greed_meteor.lua`.
*   **Damage Types:** The `damage_by_type` allows for easy modification of elemental damage contributions.