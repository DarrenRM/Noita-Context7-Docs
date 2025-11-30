---
title: Freezing Gaze Beam Projectile
category: entities
---

---

# Freezing Gaze Beam Projectile

This document details the `freezing_gaze_beam.xml` entity, which defines the behavior and properties of the Freezing Gaze beam projectile in Noita. This projectile is designed to freeze liquids and inflict a short-duration freezing effect on enemies.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="-1"`: No air friction applied, allowing for consistent velocity.
    *   `mass="0.04"`: A small mass, contributing to its projectile behavior.

### Projectile (`ProjectileComponent`)

This is the primary component defining the projectile's unique characteristics.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's trajectory arc.
*   **`speed_min="220"`, `speed_max="220"`**: The projectile travels at a fixed speed of 220 units.
*   **`lifetime="25"`**: The projectile exists for 25 frames before expiring.
*   **`damage="0.0"`**: The projectile itself deals no direct damage.
*   **`on_collision_die="1"`**: The projectile is destroyed upon colliding with an entity.
*   **`die_on_liquid_collision="1"`**: The projectile is destroyed upon colliding with any liquid.
*   **`penetrate_entities="1"`**: The projectile can pass through multiple entities.
*   **`bounces_left="10"`**: The projectile can bounce up to 10 times.
*   **`knockback_force="1.0"`**: Applies a knockback force to entities it hits.
*   **`physics_impulse_coeff="2000"`**: A high coefficient for physics impulse, indicating a strong impact.
*   **`camera_shake_when_shot="5.0"`**: Triggers a camera shake of magnitude 5.0 when the projectile is fired.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_laser.xml"`**: Specifies the muzzle flash particle effect.
*   **`shoot_light_flash_radius="180"`, `shoot_light_flash_r="30"`, `shoot_light_flash_g="170"`, `shoot_light_flash_b="210"`**: Defines the light flash properties upon shooting.
*   **`damage_game_effect_entities="data/entities/misc/effect_frozen_short.xml,"`**: This is a key attribute. When the projectile hits an entity, it applies the `effect_frozen_short.xml` game effect, which likely causes a temporary freezing status.
*   **`damage_by_type ice="0.4"`**: While the projectile itself deals no direct damage, this indicates it contributes 0.4 "ice damage" which might be used by other game mechanics or effects.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   **`radius="150"`**: The light extends to a radius of 150 units.
*   **`r="30"`, `g="90"`, `b="30"`**: The light color is a bluish-green.

### Particle Emitter (`ParticleEmitterComponent`)

Generates cosmetic particles to enhance the visual effect.

*   **`emitted_material_name="spark_blue"`**: The particles emitted are of the "spark\_blue" material.
*   **`count_min="1"`, `count_max="2"`**: Emits 1 to 2 particles per emission.
*   **`lifetime_min="0.1"`, `lifetime_max="0.8"`**: Particles have a short lifespan.
*   **`is_emitting="1"`**: The particle emitter is active.

### Magic Convert Material Components (`MagicConvertMaterialComponent`)

These components are responsible for altering the materials they come into contact with.

*   **First `MagicConvertMaterialComponent`**:
    *   **`from_material_array="water,water_ice,water_salt,water_fading,water_static,fire,lava,water_swamp,radioactive_liquid,acid,blood_cold,blood,poison,slime"`**: Specifies a wide range of materials that can be converted.
    *   **`to_material_array="ice_static,ice_static,ice_static,ice_static,ice_static,air,rock_static,ice_static,ice_radioactive_static,ice_acid_static,ice_cold_static,ice_blood_static,ice_poison_static,ice_slime_static"`**: Defines the target materials. Most liquids are converted to various forms of ice, fire to air, and lava to rock.
    *   **`steps_per_frame="20"`**: The conversion process is detailed, occurring over 20 steps per frame.
    *   **`loop="1"`**: The conversion effect will loop.
    *   **`radius="20"`**: The conversion radius is 20 units.

*   **Second `MagicConvertMaterialComponent`**:
    *   **`kill_when_finished="0"`**: This conversion effect does not necessarily end when finished.
    *   **`extinguish_fire="1"`**: Specifically designed to extinguish fire.
    *   **`is_circle="1"`**: The effect is circular.
    *   **`loop="1"`**: The effect will loop.
    *   **`radius="30"`**: The conversion radius is 30 units.

### Audio Component (`AudioComponent`)

Handles the sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank file.
*   **`event_root="player_projectiles/freezing_gaze"`**: Defines the root event for freezing gaze projectile sounds.

## Summary of Key Attributes for Modding

| Attribute Name                 | Value