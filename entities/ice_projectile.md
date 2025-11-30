---
title: Ice Projectile
category: entities
---

# Ice Projectile

This document details the configuration of the "Ice" projectile entity in Noita, focusing on its behavior, visual representation, and effects.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="10"`: Applies a moderate downward gravitational pull.
    *   `air_friction="0.05"`: Introduces a slight resistance to movement in the air.
    *   `mass="0.055"`: Defines the projectile's mass, influencing its interaction with physics.

### Projectile Behavior (`<ProjectileComponent>`)

This is the primary component defining the projectile's actions and interactions.

*   **`speed_min="50"`, `speed_max="50"`**: The projectile travels at a constant speed of 50.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not harm the entity that fired it.
*   **`damage="0"`**: The projectile itself deals no direct damage.
*   **`lifetime="80"`**: The projectile exists for 80 frames before expiring.
*   **`damage_game_effect_entities="data/entities/misc/effect_frozen_short.xml,"`**: Upon dealing damage, it applies a short-term freezing effect defined in `effect_frozen_short.xml`.
*   **`knockback_force="1.3"`**: Applies a knockback force of 1.3 to entities it hits.

#### Damage by Type (`<damage_by_type>`)

*   `ice="0.3"`: This projectile deals 0.3 damage of the "ice" type.

#### Explosion Configuration (`<config_explosion>`)

*   `damage="0.3"`: The explosion deals 0.3 damage.
*   `camera_shake="1.5"`: Triggers a moderate camera shake upon explosion.
*   `explosion_radius="6"`: The explosion affects an area with a radius of 6.
*   `explosion_sprite="data/particles/explosion_016_plasma.xml"`: Uses a plasma explosion sprite for visual effect.
*   `create_cell_probability="60"`: There's a 60% chance to create a "blood\_cold" cell upon explosion.
*   `create_cell_material="blood_cold"`: The material of the created cell is "blood\_cold".
*   `hole_enabled="1"`: Creates a hole in surfaces upon explosion.
*   `hole_image="data/temp/explosion_hole.png"`: Uses a specific image for the explosion hole.
*   `physics_explosion_power.min="0.05"`, `physics_explosion_power.max="0.12"`: Defines the range of physics-based force applied by the explosion.
*   `shake_vegetation="1"`: Causes vegetation to shake when the explosion occurs.
*   `stains_enabled="1"`, `stains_radius="9"`: Enables stains with a radius of 9.
*   `ray_energy="5000"`: The explosion has a ray energy value of 5000.

### Visual Representation (`<SpriteComponent>`)

*   `image_file="data/projectiles_gfx/ice.xml"`: Specifies the graphical asset for the projectile.
*   `offset_x="8"`, `offset_y="6"`: Adjusts the sprite's position relative to the entity's origin.

### Particle Effects (`<ParticleEmitterComponent>`)

Two particle emitters are used to create visual effects:

1.  **Cold Vapor Emission**:
    *   `emitted_material_name="blood_cold_vapour"`: Emits particles of "blood\_cold\_vapour".
    *   `fade_based_on_lifetime="1"`: Particles fade as their lifetime decreases.
    *   `count_min="5"`, `count_max="5"`: Emits a consistent number of particles.
    *   `lifetime_min="0.1"`, `lifetime_max="0.3"`: Particles have a short lifespan.
    *   `emit_cosmetic_particles="1"`: These are cosmetic particles, not affecting gameplay physics.

2.  **Custom Style Emission**:
    *   `emitted_material_name="blood_cold_vapour"`: Also emits "blood\_cold\_vapour".
    *   `custom_style="FIRE"`: Applies a "FIRE" style to the particles.
    *   `color="ff50e7f0"`: Sets a specific bluish-purple color for these particles.
    *   `count_min="1"`, `count_max="3"`: Emits a small, variable number of particles.
    *   `lifetime_min="0.1"`, `lifetime_max="0.3"`: Short particle lifespan.

### Lighting (`<LightComponent>`)

*   `radius="20"`: The projectile emits light in a radius of 20.
*   `r="99"`, `g="205"`, `b="139"`: Sets the light color to a pale cyan/green.

### Audio (`<AudioComponent>`)

*   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
*   `event_root="projectiles/icethrower"`: Links to the "icethrower" sound event.

### Variable Storage (`<VariableStorageComponent>`)

*   `name="projectile_file"`: Stores the path to this projectile's XML file.
*   `value_string="data/entities/projectiles/ice.xml"`: The value is the file path itself.