---
title: Boss Centipede Shield Weak
category: entities
---

# Boss Centipede Shield Weak

This entity defines the visual and functional components of the Boss Centipede's shield when it is in a weakened state. It primarily consists of particle effects and a light source to indicate the shield's presence and state.

## Key Components

### EnergyShieldComponent

This component governs the shield's behavior.

*   **`_tags`**: `shield,disabled_at_start` - Indicates this is a shield and is disabled when the entity first spawns.
*   **`_enabled`**: `0` - The shield is initially inactive.
*   **`recharge_speed`**: `0.8` - The rate at which the shield recharges.
*   **`radius`**: `50.0` - The radial extent of the shield.

### ParticleEmitterComponent (Main Shield Visual)

This component creates the primary visual effect for the shield.

*   **`_tags`**: `shield,disabled_at_start` - Identifies this as a shield particle effect, initially disabled.
*   **`_enabled`**: `0` - The particle emitter is initially inactive.
*   **`emitted_material_name`**: `plasma_fading` - The material used for the emitted particles.
*   **`lifetime_min`**: `0.1` - Minimum duration of each particle.
*   **`lifetime_max`**: `0.5` - Maximum duration of each particle.
*   **`count_min`**: `6` - Minimum number of particles emitted per interval.
*   **`count_max`**: `12` - Maximum number of particles emitted per interval.
*   **`area_circle_radius.max`**: `50` - The maximum radius of the emission area.
*   **`is_emitting`**: `1` - The emitter is set to continuously emit particles when enabled.

### ParticleEmitterComponent (Shield Ring)

This component creates a ring effect around the shield.

*   **`_tags`**: `shield,disabled_at_start,shield_ring` - Identifies this as a shield ring particle effect, initially disabled.
*   **`_enabled`**: `0` - The particle emitter is initially inactive.
*   **`emitted_material_name`**: `plasma_fading` - The material used for the emitted particles.
*   **`lifetime_min`**: `0.02` - Minimum duration of each particle.
*   **`lifetime_max`**: `0.05` - Maximum duration of each particle.
*   **`count_min`**: `200` - Minimum number of particles emitted per interval.
*   **`count_max`**: `300` - Maximum number of particles emitted per interval.
*   **`area_circle_radius.min`**: `50` - The minimum radius of the emission area.
*   **`area_circle_radius.max`**: `50` - The maximum radius of the emission area, creating a distinct ring.
*   **`is_emitting`**: `1` - The emitter is set to continuously emit particles when enabled.

### ParticleEmitterComponent (Shield Hit)

This component generates particles when the shield is hit.

*   **`_tags`**: `shield,disabled_at_start,shield_hit` - Identifies this as a shield hit particle effect, initially disabled.
*   **`_enabled`**: `0` - The particle emitter is initially inactive.
*   **`emitted_material_name`**: `plasma_fading` - The material used for the emitted particles.
*   **`lifetime_min`**: `0.3` - Minimum duration of each particle.
*   **`lifetime_max`**: `1` - Maximum duration of each particle.
*   **`count_min`**: `500` - Minimum number of particles emitted per interval.
*   **`count_max`**: `860` - Maximum number of particles emitted per interval.
*   **`area_circle_radius.min`**: `50` - The minimum radius of the emission area.
*   **`area_circle_radius.max`**: `50` - The maximum radius of the emission area.
*   **`is_emitting`**: `0` - This emitter is designed to be triggered, not continuously active.

### LightComponent

This component adds a light source to the shield.

*   **`_tags`**: `shield,disabled_at_start,shield_hit` - Identifies this as a shield light effect, initially disabled.
*   **`_enabled`**: `0` - The light source is initially inactive.
*   **`radius`**: `80` - The radius of the light's influence.
*   **`fade_out_time`**: `1.5` - The time it takes for the light to fade out.
*   **`r`, `g`, `b`**: `150`, `190`, `230` - Defines the color of the light (a bluish-white).

### AudioComponent

This component handles the sound effects associated with the shield.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/shield` - The root event name for shield-related sounds.
*   **`set_latest_event_position`**: `1` - Ensures the sound plays at the entity's current position.