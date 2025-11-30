---
title: Rubber Ball Projectile
category: entities
---

# Rubber Ball Projectile

This document details the configuration for the "Rubber Ball" projectile entity in Noita, intended for AI-assisted modding.

## Entity Definition

The `rubber_ball.xml` file defines a projectile with specific physical properties, behaviors, and visual/audio components.

```xml
<Entity
  name="$projectile_default" tags="projectile_player">
  <!-- ... other components ... -->
</Entity>
```

## Key Components

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="250"`: Applies a downward gravitational force.
    *   `air_friction="0.6"`: Controls air resistance.
    *   `mass="0.03"`: Defines the projectile's mass.

### Projectile Behavior (`ProjectileComponent`)

This is the core component defining the projectile's unique characteristics.

*   **`_enabled="1"`**: Ensures the component is active.
*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the minimum and maximum "lob" or arc of the projectile.
*   **`speed_min="650"`, `speed_max="750"`**: Sets the range for the projectile's initial speed.
*   **`friction="1"`**: High friction, suggesting it might slow down quickly or interact significantly with surfaces.
*   **`direction_random_rad="0.01"`**: Introduces a small amount of randomness to the projectile's initial direction.
*   **`on_death_explode="0"`**: The projectile does not explode upon death.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision with a surface.
*   **`lifetime="750"`**: The maximum duration the projectile exists in frames.
*   **`damage="0.12"`**: The base damage dealt by the projectile.
*   **`damage_scaled_by_speed="1"`**: Damage increases with projectile speed.
*   **`bounce_always="1"`**: The projectile will always attempt to bounce.
*   **`bounces_left="10"`**: The projectile can bounce a maximum of 10 times.
*   **`bounce_energy="0.9"`**: Retains 90% of its energy after each bounce, indicating it's quite bouncy.
*   **`bounce_fx_file="data/entities/particles/bounce_effects/rubber_ball.xml"`**: Specifies the particle effect to play upon bouncing.
*   **`velocity_sets_rotation="1"`**: The projectile's rotation is determined by its velocity.
*   **`knockback_force="0.4"`**: Applies a small knockback effect to targets it hits.
*   **`physics_impulse_coeff="1200"`**: A high coefficient for physics impulse, suggesting strong interactions.

### Sprite (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/rubber_ball.xml"`**: Links to the sprite definition for the rubber ball.

### Audio (`AudioComponent`)

Handles sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing projectile sounds.
*   **`event_root="player_projectiles/bullet_rubber_ball"`**: The specific sound event for this projectile.

### Particle Emitter (`ParticleEmitterComponent`)

Creates visual effects, in this case, a trail.

*   **`emitted_material_name="plasma_fading_green"`**: The material used for the emitted particles.
*   **`is_trail="1"`**: Indicates this emitter is for a trail effect.
*   **`create_real_particles="0"`**: Particles are cosmetic and do not have physical presence.
*   **`emit_cosmetic_particles="1"`**: Ensures cosmetic particles are emitted.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/deck/rubber_ball.xml"`**: The value, referencing its own file path.