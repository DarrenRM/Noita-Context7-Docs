---
title: Magic Shield Part Projectile
category: entities
---

# Magic Shield Part Projectile

This entity defines a projectile that functions as a component of a magic shield. It's designed to be a persistent, low-damage projectile that contributes to a shield effect.

## Key Components

### Base Projectile (`BaseComponent`)

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="0"`**: No air resistance acts on the projectile.

### Projectile Behavior (`ProjectileComponent`)

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile.
*   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial speed.
*   **`die_on_low_velocity="0"`**: The projectile will not die if its velocity becomes very low.
*   **`on_death_explode="0"`**: The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No graphical effects are left behind when the projectile dies.
*   **`on_lifetime_out_explode="0"`**: The projectile does not explode when its lifetime ends.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion were to occur, it wouldn't damage the shooter.
*   **`penetrate_entities="1"`**: The projectile can pass through entities.
*   **`damage="0.05"`**: Deals a very small amount of damage.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`damage_every_x_frames="20"`**: Damage is applied every 20 frames.
*   **`lifetime="500"`**: The projectile exists for 500 frames.

### Visuals (`SpriteComponent`)

*   **`image_file="data/particles/star.xml"`**: Uses a star particle for its visual representation.
*   **`offset_x="6"`, `offset_y="6"`**: Offsets the sprite's position.
*   **`additive="1"`**: The sprite uses additive blending.
*   **`rect_animation="spawn"`**: Uses a "spawn" animation.

### Lighting (`LightComponent`)

*   **`radius="90"`**: The light emitted has a radius of 90 units.
*   **`r="30"`, `g="95"`, `b="160"`**: Defines the light color as a bluish hue.

### Particle Emission (`ParticleEmitterComponent`)

This entity uses two identical `ParticleEmitterComponent`s to emit `plasma_fading` particles.

*   **`emitted_material_name="plasma_fading"`**: The type of particle emitted.
*   **`lifetime_min="0.1"`, `lifetime_max="0.8"`**: Particles have a short lifespan.
*   **`count_min="1"`, `count_max="1"`**: Emits one particle at a time.
*   **`fade_based_on_lifetime="1"`**: Particles fade as their lifetime decreases.
*   **`cosmetic_force_create="0"`**: Not a cosmetic particle.
*   **`airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.05"`**: Minor airflow effects on particles.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`is_emitting="1"`**: The emitter is active.

### Scripting (`LuaComponent`)

*   **`script_source_file="data/scripts/projectiles/magic_shield_part.lua"`**: Links to a Lua script for custom behavior.
*   **`execute_every_n_frame="1"`**: The script executes every frame.

### Energy Shield (`EnergyShieldComponent`)

*   **`recharge_speed="0.25"`**: The shield recharges at a speed of 0.25.
*   **`max_energy="0.8"`**: The maximum energy capacity of the shield is 0.8.
*   **`energy="0.8"`**: The shield starts with 0.8 energy.
*   **`radius="8"`**: The shield has a radius of 8 units.

### Audio (`AudioComponent`, `AudioLoopComponent`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: Uses the projectiles audio bank.
*   **`event_root="player_projectiles/magic_shield"`**: Sets the root event for player projectile magic shield sounds.
*   **`event_name="player_projectiles/magic_shield/loop"`**: Specifies the loop event for the shield sound.
*   **`auto_play="1"`**: The loop sound plays automatically.