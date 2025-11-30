---
title: Necrobot Super Revive Entity
category: entities
---

---

# Necrobot Super Revive Entity

This entity defines the visual and auditory effects associated with the Necrobot's "super revive" ability. It primarily focuses on particle effects and sound.

## Key Components

### SpriteComponent
This component defines the visual representation of the revive effect.

*   **image_file**: `data/particles/skullface_red.xml` - Specifies the texture used for the effect.
*   **additive**: `1` - Enables additive blending for a brighter, more intense visual.
*   **emissive**: `1` - Makes the sprite emit light.

### LuaComponent
This component triggers a Lua script to handle the logic of the super revive.

*   **script_source_file**: `data/scripts/status_effects/necrobot_super_end.lua` - The script responsible for the revive's behavior.
*   **execute_every_n_frame**: `120` - The script is executed periodically.

### ParticleEmitterComponent
This component generates cosmetic particles to enhance the visual impact of the revive.

*   **emitted_material_name**: `spark_red` - The type of particle to emit.
*   **x_pos_offset_min/max**, **y_pos_offset_min/max**: Defines the area where particles are spawned.
*   **x_vel_min/max**, **y_vel_min/max**: Controls the initial velocity of the emitted particles.
*   **count_min/max**: The number of particles emitted per burst.
*   **lifetime_min/max**: The duration each particle exists.
*   **emission_interval_min_frames/max_frames**: Controls the rate at which particles are emitted.
*   **emit_cosmetic_particles**: `1` - Ensures these are cosmetic particles, not affecting gameplay directly.

### AudioComponent
This component plays a sound effect associated with the revive.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **event_root**: `projectiles/revive` - The specific sound event to trigger.