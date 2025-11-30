---
title: Big Orb Projectile
category: entities
---

---

# Big Orb Projectile

This document describes the `orb_big.xml` entity, which defines a large, homing projectile with explosive properties. It's likely used by a boss enemy.

## Key Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile behavior.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.8"`: A relatively low mass.

### Homing Behavior (`HomingComponent`)

This projectile actively seeks out targets.

*   `target_tag="prey"`: It targets entities tagged as "prey".
*   `homing_targeting_coeff="8"`: A strong coefficient for homing.
*   `detect_distance="350"`: Can detect targets up to 350 units away.
*   `homing_velocity_multiplier="1.0"`: Homing doesn't alter its base speed.

### Projectile Mechanics (`ProjectileComponent`)

Defines the core projectile attributes and its death behavior.

*   `lob_min="0.8"`, `lob_max="1.0"`: Controls the arc of the projectile.
*   `speed_min="100"`, `speed_max="120"`: The projectile's speed range.
*   `die_on_low_velocity="0"`: Does not die if its speed drops too low.
*   `on_death_explode="1"`: Explodes upon death.
*   `on_lifetime_out_explode="1"`: Explodes when its lifetime expires.
*   `explosion_dont_damage_shooter="1"`: The explosion will not harm the entity that fired it.
*   `damage="1.8"`: Base damage dealt by the projectile itself.
*   `on_collision_die="1"`: Dies upon colliding with something.
*   `lifetime="130"`: The projectile exists for 130 frames before expiring.
*   `knockback_force="2.0"`: Applies a knockback force on impact.

#### Explosion Configuration (`config_explosion`)

Details of the explosion that occurs on death.

*   `never_cache="1"`: Prevents caching of this explosion.
*   `camera_shake="4.0"`: Causes significant camera shake.
*   `explosion_radius="30"`: The radius of the explosion.
*   `explosion_sprite="data/particles/explosion_032.xml"`: The visual effect for the explosion.
*   `create_cell_probability="1"`: Always creates a cell upon explosion.
*   `create_cell_material="acid"`: The material of the created cell is acid.
*   `ray_energy="10000"`: High energy for potential ray interactions.
*   `hole_destroy_liquid="1"`: The explosion can destroy liquids.
*   `hole_enabled="1"`: Creates holes in terrain.
*   `damage="1.2"`: Damage dealt by the explosion itself.
*   `physics_explosion_power.min="0.4"`, `physics_explosion_power.max="0.6"`: The force of the physics-based explosion.
*   `sparks_enabled="1"`: Sparks are generated.
*   `spark_material="spark_red"`: The material of the sparks.
*   `light_r="155"`, `light_g="15"`, `light_b="140"`: Defines the color of the light emitted by the explosion.

### Visuals (`SpriteComponent`)

Defines the appearance of the projectile.

*   `image_file="data/projectiles_gfx/slimeball_huge_red.xml"`: Specifies the sprite sheet used.
*   `rect_animation="fireball"`: Uses an animation named "fireball".

### Particle Emitter (`ParticleEmitterComponent`)

Generates cosmetic particles.

*   `emitted_material_name="spark_red"`: Emits red sparks.
*   `count_min="5"`, `count_max="9"`: Emits between 5 and 9 particles per emission.
*   `lifetime_min="0.3"`, `lifetime_max="1.6"`: Particles have a short lifespan.
*   `is_emitting="1"`: The emitter is active.

### Light Source (`LightComponent`)

Provides illumination.

*   `radius="150"`: The radius of the light.
*   `r="180"`, `g="35"`, `b="60"`: A reddish light color.

### Audio (`AudioComponent`)

Handles sound effects.

*   `file="data/audio/Desktop/projectiles.bank"`: The audio bank used.
*   `event_root="projectiles/orb_b"`: The root event for projectile sounds.

### Variable Storage (`VariableStorageComponent`)

Stores projectile-specific variables.

*   `name="projectile_file"`: Stores the path to this entity's XML file.
*   `value_string="data/entities/animals/boss_meat/orb_big.xml"`: The value is the path to this file.

### Hit Effect (`HitEffectComponent`)

Applies an effect upon hitting something.

*   `effect_hit="LOAD_CHILD_ENTITY"`: Loads another entity as a hit effect.
*   `value_string="data/entities/misc/curse_init.xml"`: The entity to load is `curse_init.xml`.