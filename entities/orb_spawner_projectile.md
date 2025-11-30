---
title: Orb Spawner Projectile
category: entities
---

# Orb Spawner Projectile

This entity defines a projectile that spawns orbs. It's a versatile projectile with custom explosion behavior and particle effects.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="1"`: No air friction applied.
    *   `mass="0.06"`: Defines the projectile's mass.

### Projectile Component (`<ProjectileComponent>`)

This is the core component defining the projectile's behavior.

*   **`_enabled="1"`**: Enables the component.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior of the projectile.
*   **`speed_min="120"`, `speed_max="120"`**: Sets the projectile's speed.
*   **`die_on_low_velocity="0"`**: The projectile does not die when its velocity becomes low.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not damage the entity that fired it.
*   **`bounce_always="1"`**: The projectile always bounces off surfaces.
*   **`damage="0.1"`**: The projectile deals minimal damage.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_large_pink.xml"`**: Specifies the muzzle flash particle effect.
*   **`shoot_light_flash_r="255"`, `shoot_light_flash_g="40"`, `shoot_light_flash_b="240"`, `shoot_light_flash_radius="90"`**: Defines the color and radius of the light flash when the projectile is shot.
*   **`lifetime="200"`**: The projectile's lifespan in frames.

#### `config_explosion`

*   **`never_cache="1"`**: Prevents caching of the explosion.
*   **`camera_shake="0"`**: No camera shake on explosion.
*   **`explosion_radius="10"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_016_plasma.xml"`**: The sprite used for the explosion.
*   **`ray_energy="10000"`**: The energy of the explosion's rays.
*   **`hole_destroy_liquid="1"`**: The explosion can destroy liquids.
*   **`explosion_sprite_emissive="1"`, `explosion_sprite_additive="1"`**: Controls the visual properties of the explosion sprite.
*   **`hole_enabled="1"`**: Enables the creation of holes by the explosion.
*   **`physics_explosion_power.min="0.2"`, `physics_explosion_power.max="0.3"`**: The minimum and maximum physics force applied by the explosion.
*   **`physics_throw_enabled="1"`**: Physics objects are thrown by the explosion.
*   **`shake_vegetation="1"`**: Vegetation is shaken by the explosion.
*   **`audio_event_name="explosions/magic_small"`**: The sound event played on explosion.

### Particle Emitter Component (`<ParticleEmitterComponent>`)

This component controls the cosmetic particles emitted by the projectile.

*   **`emitted_material_name="spark_blue"`**: The material of the emitted particles.
*   **`count_min="30"`, `count_max="50"`**: The number of particles emitted.
*   **`area_circle_radius.min="4"`, `area_circle_radius.max="4"`**: The radius of the emission area.
*   **`velocity_always_away_from_center="80"`**: Particles are always emitted away from the center.
*   **`lifetime_min="0.9"`, `lifetime_max="3.2"`**: The lifespan of the emitted particles.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`emission_interval_min_frames="16"`, `emission_interval_max_frames="16"`**: The interval between particle emissions.

### Sprite Components (`<SpriteComponent>`)

Two sprite components are used, likely for different rendering layers or effects.

*   **`image_file="data/projectiles_gfx/orb_blue.xml"`**: The sprite image file.
*   **`rect_animation="spawn"`**: Uses a "spawn" animation.
*   The second sprite component has `emissive="1"` and `additive="1"`, suggesting it contributes to a glowing or additive visual effect.

### Lua Component (`<LuaComponent>`)

*   **`script_source_file="data/scripts/projectiles/orb.lua"`**: Links to an external Lua script for custom logic.
*   **`execute_every_n_frame="15"`**: The script executes every 15 frames.

### Light Component (`<LightComponent>`)

*   **`radius="150"`**: The radius of the light emitted by the projectile.
*   **`r="45"`, `g="45"`, `b="90"`**: The color of the light (a purplish hue).

### Audio Component (`<AudioComponent>`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank file.
*   **`event_root="projectiles/orb_a"`**: The root event name for projectile sounds.

### Variable Storage Component (`<VariableStorageComponent>`)

*   **`name="projectile_file"`**: Stores the path to this projectile's XML file.
*   **`value_string="data/entities/projectiles/orbspawner.xml"`**: The value of the stored variable.