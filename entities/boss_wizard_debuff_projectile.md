---
title: Boss Wizard Debuff Projectile
category: entities
---

# Boss Wizard Debuff Projectile

This entity defines the projectile used by the Boss Wizard that applies a debuff. It primarily consists of particle effects for visual representation and a Lua script to handle the debuff logic.

## Key Components

### ParticleEmitterComponent

This component controls the visual effects of the projectile.

*   **`emitted_material_name`**: `spark_purple` - Specifies the material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `0.8` / `5.5` - Duration of individual particles in seconds.
*   **`count_min` / `count_max`**: `20` / `40` - Number of particles emitted per burst.
*   **`airflow_force`**: `1.1` - Controls the force applied by airflow to particles.
*   **`image_animation_file`**: `data/particles/image_emitters/aura.png` - The sprite sheet used for particle animation.
*   **`image_animation_speed`**: `3.5` - Speed of the particle animation.

### LuaComponent

This component executes the debuff logic associated with the projectile.

*   **`script_source_file`**: `data/entities/animals/boss_wizard/debuff.lua` - The Lua script file containing the debuff implementation.
*   **`execute_every_n_frame`**: `70` - The frequency (in frames) at which the script's logic is executed.

### AudioComponent

This component handles the sound effects for the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `projectiles/polymorph_bubble` - The specific sound event to play.