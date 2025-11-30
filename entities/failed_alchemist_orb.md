---
title: Failed Alchemist Orb
category: entities
---

# Failed Alchemist Orb

This document details the configuration of the "Failed Alchemist Orb" entity in Noita, focusing on its visual, behavioral, and functional attributes relevant to modding.

## Core Entity Attributes

The `Entity` tag defines the fundamental properties of the orb.

*   **`name`**: "unknown" - This is a placeholder and can be renamed for clarity in mods.
*   **`tags`**: "hittable,mortal,homing_target" - These tags dictate how the orb interacts with the game world, allowing it to be hit, be subject to damage, and potentially be targeted by homing effects.

## Visual Components

### SpriteComponent

This component handles the visual representation of the orb.

*   **`image_file`**: "data/buildings_gfx/failed_alchemist_orb.xml" - Specifies the graphical asset used for the orb.
*   **`alpha`**: "1" - Controls the transparency of the sprite (1 being fully opaque).
*   **`offset_x`, `offset_y`**: "0" - Defines the sprite's position relative to the entity's origin.

### ParticleEmitterComponent

This component generates cosmetic particles around the orb.

*   **`emitted_material_name`**: "plasma_fading_pink" - The material used for the emitted particles.
*   **`x_pos_offset_min`/`max`, `y_pos_offset_min`/`max`**: Defines the area where particles are spawned relative to the orb.
*   **`x_vel_min`/`max`, `y_vel_min`/`max`**: Sets the initial velocity range for the particles.
*   **`gravity.y`**: "0.0" - Particles are not affected by gravity.
*   **`count_min`/`max`**: "4" - The number of particles emitted per burst.
*   **`lifetime_min`/`max`**: "0.1" to "1.5" - The duration particles exist.
*   **`emission_interval_min_frames`/`max_frames`**: "2" - Particles are emitted frequently.
*   **`is_emitting`**: "1" - The particle emitter is active.

## Behavioral Components

### LuaComponent

These components define the orb's scripting logic.

*   **`script_source_file`**: "data/scripts/buildings/failed_alchemist_orb.lua" - The primary script governing the orb's behavior.
*   **`execute_every_n_frame`**: "220" - The main script runs periodically, every 220 frames.
*   **`script_death`**: "data/scripts/buildings/failed_alchemist_orb_death.lua" - A separate script executed when the orb is destroyed.

### HitboxComponent

Defines the collision area of the orb.

*   **`aabb_min_x`/`max_x`**: "-8" to "8" - The horizontal bounds of the hitbox.
*   **`aabb_min_y`/`max_y`**: "-12" to "4" - The vertical bounds of the hitbox.

### DamageModelComponent

Manages the orb's health and damage interactions.

*   **`hp`**: "2.5" - The orb's health points.
*   **`blood_material`**: "spark_purple_bright" - The material that appears when the orb takes damage.
*   **`ragdoll_fx_forced`**: "DISINTEGRATED" - The visual effect upon destruction.
*   **`ragdoll_material`**: "crystal_purple" - The material associated with the disintegration effect.
*   **`damage_multipliers`**:
    *   `drill`: "0.4" - Reduced damage from drills.
    *   `fire`, `freeze`, `slice`: "0.0" - Immune to fire, freezing, and slicing damage.

## Special Effects

The orb grants specific resistances to entities that inherit its transform.

### Entity with GameEffectComponent (Electricity Protection)

*   **`effect`**: "PROTECTION_ELECTRICITY" - Grants immunity or resistance to electricity.
*   **`frames`**: "-1" - The effect is permanent.

### Entity with GameEffectComponent (Freeze Protection)

*   **`effect`**: "PROTECTION_FREEZE" - Grants immunity or resistance to freezing.
*   **`frames`**: "-1" - The effect is permanent.

## Audio Components

### AudioComponent

Plays a specific sound event when the orb is active.

*   **`file`**: "data/audio/Desktop/animals.bank" - The audio bank containing the sound.
*   **`event_root`**: "animals/failed_alchemist_b_orb" - The root event name.

### AudioLoopComponent

Plays a looping sound effect.

*   **`file`**: "data/audio/Desktop/animals.bank" - The audio bank.
*   **`event_name`**: "animals/failed_alchemist_b_orb/orb_loop" - The name of the looping event.
*   **`auto_play`**: "1" - The loop starts automatically.