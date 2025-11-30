---
title: Spirit Slime Effect
category: entities
---

# Spirit Slime Effect

This entity defines the "Spirit Slime" status effect in Noita. It applies a "SLIMY" effect to entities and has associated visual and UI elements.

## Key Components

### GameEffectComponent
This component applies the core game effect.

*   **`_tags`**: `spirit_slime` - Identifies this specific effect.
*   **`effect`**: `SLIMY` - The actual status effect applied.
*   **`frames`**: `120` - Duration of the effect in frames.

### LifetimeComponent
Determines how long the entity itself persists.

*   **`lifetime`**: `100` - The entity will disappear after 100 frames.

### ParticleEmitterComponent
Responsible for generating visual particles associated with the effect.

*   **`emitted_material_name`**: `spark_purple_bright` - The material used for the emitted particles.
*   **`gravity.y`**: `0` - Particles are not affected by gravity.
*   **`lifetime_min`**: `0.3` - Minimum lifetime of emitted particles.
*   **`lifetime_max`**: `2` - Maximum lifetime of emitted particles.
*   **`count_min`**: `1` - Minimum number of particles emitted per interval.
*   **`count_max`**: `2` - Maximum number of particles emitted per interval.
*   **`emission_interval_min_frames`**: `1` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `4` - Maximum frames between particle emissions.
*   **`emit_cosmetic_particles`**: `1` - Cosmetic particles are emitted.
*   **`emit_real_particles`**: `0` - No "real" (physics-simulating) particles are emitted.
*   **`x_vel_min`**: `-20` - Minimum horizontal velocity of emitted particles.
*   **`x_vel_max`**: `20` - Maximum horizontal velocity of emitted particles.
*   **`y_vel_min`**: `-20` - Minimum vertical velocity of emitted particles.
*   **`y_vel_max`**: `20` - Maximum vertical velocity of emitted particles.
*   **`is_emitting`**: `1` - The particle emitter is active.

### UIIconComponent
Defines how the status effect is displayed in the UI.

*   **`name`**: `$status_slimy` - The localized name for the status effect.
*   **`description`**: `$statusdesc_slimy` - The localized description for the status effect.
*   **`icon_sprite_file`**: `data/ui_gfx/status_indicators/slimy.png` - The sprite file for the status icon.
*   **`display_in_hud`**: `1` - The icon is displayed in the Heads-Up Display.