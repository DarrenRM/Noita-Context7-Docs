---
title: Neutralized Particle Effects
category: entities
---

# Neutralized Particle Effects

This entity defines particle effects associated with a "neutralized" state, likely used for visual feedback when certain actions or states are nullified or rendered inert. It primarily utilizes two `ParticleEmitterComponent`s to generate different types of sparks.

## ProjectileComponent

This component defines the behavior of the entity as a projectile. However, most of its properties are set to zero, indicating it's not intended to function as a damaging or physically interactive projectile.

### Key Attributes:

*   `lifetime`: The duration the projectile exists before expiring.
    *   `lifetime="2"`: The projectile lasts for 2 seconds.
*   `on_lifetime_out_explode`: Determines if an explosion occurs when the lifetime ends.
    *   `on_lifetime_out_explode="1"`: An explosion effect is triggered upon expiration.
*   `damage`: The amount of damage the projectile deals.
    *   `damage="0"`: Deals no damage.

### `config_explosion`

This nested configuration defines the parameters of the explosion that occurs when `on_lifetime_out_explode` is true. All explosion-related properties are set to zero, meaning the explosion is purely visual and has no physical impact.

*   `damage="0"`: Explosion deals no damage.
*   `explosion_radius="0"`: Explosion has no radius.
*   `particle_effect="0"`: No additional particles are created by the explosion.
*   `damage_mortals="0"`: The explosion does not damage living entities.

## ParticleEmitterComponent (Blue Sparks)

This component is responsible for emitting blue sparks.

### Key Attributes:

*   `emitted_material_name`: The material used for the emitted particles.
    *   `emitted_material_name="spark_blue"`: Emits particles of the "spark\_blue" material.
*   `lifetime_min`, `lifetime_max`: The minimum and maximum lifetime of individual particles.
    *   `lifetime_min="1.5"`, `lifetime_max="2.5"`: Particles last between 1.5 and 2.5 seconds.
*   `count_min`, `count_max`: The minimum and maximum number of particles emitted per emission.
    *   `count_min="10"`, `count_max="35"`: Emits between 10 and 35 particles.
*   `area_circle_radius.max`: The maximum radius of the circular area from which particles are emitted.
    *   `area_circle_radius.max="4"`: Particles are emitted from a circle with a maximum radius of 4 units.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: The velocity range for emitted particles.
    *   `x_vel_min="-40"`, `x_vel_max="40"`, `y_vel_min="-40"`, `y_vel_max="40"`: Particles are emitted with velocities ranging from -40 to 40 in both X and Y directions.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters controlling how airflow affects the particles.
    *   `airflow_force="0.5"`, `airflow_time="1.9"`, `airflow_scale="0.15"`: These values influence the particle's movement due to airflow.

## ParticleEmitterComponent (Purple Sparks)

This component emits brighter purple sparks with a longer lifetime.

### Key Attributes:

*   `emitted_material_name`: The material used for the emitted particles.
    *   `emitted_material_name="spark_purple_bright"`: Emits particles of the "spark\_purple\_bright" material.
*   `lifetime_min`, `lifetime_max`: The minimum and maximum lifetime of individual particles.
    *   `lifetime_min="10"`, `lifetime_max="30"`: Particles last between 10 and 30 seconds.
*   `count_min`, `count_max`: The minimum and maximum number of particles emitted per emission.
    *   `count_min="5"`, `count_max="15"`: Emits between 5 and 15 particles.
*   `area_circle_radius.max`: The maximum radius of the circular area from which particles are emitted.
    *   `area_circle_radius.max="10"`: Particles are emitted from a circle with a maximum radius of 10 units.
*   `create_real_particles`, `emit_real_particles`: Indicates that these are actual game particles, not just cosmetic ones.
    *   `create_real_particles="1"`, `emit_real_particles="1"`: These are real, potentially interactable particles.
*   `emit_cosmetic_particles="0"`: These are not cosmetic particles.