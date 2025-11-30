---
title: Large Grenade Projectile
category: entities
---

# Large Grenade Projectile

This document details the configuration of the "Large Grenade" projectile entity in Noita, useful for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag, with specific attributes and components dictating its behavior.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... components ... -->
</Entity>
```

-   **`name="$projectile_default"`**: A placeholder name, often overridden by specific projectile types.
-   **`tags="projectile_player"`**: Identifies this entity as a projectile fired by the player.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

#### Velocity Component (`<VelocityComponent>`)

Defines the physical movement characteristics.

-   **`mass="0.165"`**: The mass of the projectile, affecting its inertia and how it interacts with physics.
-   **`gravity_y="1000"`**: The acceleration due to gravity applied to the projectile along the Y-axis.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component that governs the projectile's unique behaviors and effects.

-   **`_enabled="1"`**: Enables this component.
-   **`lob_min="0.9"`, `lob_max="1.0"`**: Controls the "lob" or arc of the projectile. Values closer to 1 mean a straighter trajectory.
-   **`speed_min="50"`, `speed_max="80"`**: The range of initial speeds the projectile can have.
-   **`friction="0.6"`**: How much air resistance or friction affects the projectile's speed over time.
-   **`direction_random_rad="0.05"`**: Introduces a small amount of randomness to the projectile's initial direction.
-   **`on_death_explode="1"`**: Triggers an explosion when the projectile dies (e.g., hits a surface or its lifetime ends).
-   **`on_lifetime_out_explode="1"`**: Triggers an explosion when the projectile's `lifetime` expires.
-   **`on_collision_die="1"`**: The projectile will be destroyed upon colliding with something.
-   **`lifetime="500"`**: The maximum duration (in frames) the projectile exists before expiring.
-   **`damage="2.0"`**: The base damage dealt by the projectile.
-   **`camera_shake_when_shot="15.0"`**: The intensity of camera shake when this projectile is fired.
-   **`bounces_left="1"`**: The number of bounces the projectile can perform before being destroyed.
-   **`knockback_force="1.0"`**: The force applied to entities that are hit by this projectile.

#### Damage by Type (`<damage_by_type>`)

Allows for specific damage multipliers against certain damage types.

-   **`fire="1.8"`**: Deals 1.8 times the base damage to entities vulnerable to fire.

#### Explosion Configuration (`<config_explosion>`)

Defines the properties of the explosion that occurs when `on_death_explode` or `on_lifetime_out_explode` is triggered.

-   **`camera_shake="50"`**: The intensity of camera shake caused by the explosion.
-   **`explosion_radius="16"`**: The radius of the explosion's effect.
-   **`explosion_sprite="data/particles/explosion_016.xml"`**: The visual effect used for the explosion.
-   **`load_this_entity="data/entities/particles/particle_explosion/main_gunpowder_small.xml"`**: The entity to load and spawn when the explosion occurs.
-   **`hole_enabled="1"`**: Enables the creation of holes in terrain by the explosion.
-   **`ray_energy="450000"`**: The energy of the destructive rays emitted by the explosion.
-   **`damage="3.9"`**: The damage dealt by the explosion itself.
-   **`physics_explosion_power.min="0.3"`, `physics_explosion_power.max="0.6"`**: The minimum and maximum force applied to physics objects by the explosion.
-   **`audio_event_name="explosions/magic_grenade_mid"`**: The sound event to play when the explosion occurs.

### Sprite Component (`<SpriteComponent>`)

Handles the visual representation of the projectile.

-   **`image_file="data/projectiles_gfx/grenade_large.xml"`**: Specifies the graphical asset for the projectile.
-   **`offset_x="6"`, `offset_y="6"`**: Adjusts the sprite's position relative to the projectile's origin.
-   **`additive="1"`**: Enables additive blending for the sprite, often used for glowing or emissive effects.

### Particle Emitter Components (`<ParticleEmitterComponent>`)

These components spawn particles to create visual effects.

-   **`emitted_material_name="..."`**: Specifies the type of material to emit (e.g., `smoke`, `fire`, `spark`).
-   **`count_min`, `count_max`**: The range of particles to emit per emission.
-   **`lifetime_min`, `lifetime_max`**: The duration particles exist.
-   **`create_real_particles="1"`**: Spawns actual physics-enabled particles.
-   **`emit_cosmetic_particles="1"`**: Spawns visual-only particles.
-   **`is_emitting="1"`**: Enables the particle emitter.

### Audio Component (`<AudioComponent>`)

Manages sound effects associated with the projectile.

-   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound events.
-   **`event_root="player_projectiles/bullet_launcher"`**: The specific sound event to play.

### Light Component (`<LightComponent>`)

Adds a light source to the projectile.

-   **`radius="60"`**: The radius of the light.
-   **`r="120"`, `g="80"`, `b="10"`**: The RGB color values of the light.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores custom variables.

-   **`name="projectile_file"`**: The name of the variable.
-   **`value_string="data/entities/projectiles/deck/grenade_large.xml"`**: The value, often used to reference the projectile's own entity file.