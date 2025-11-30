---
title: Gold Pickup Particle Entity
category: entities
---

# Gold Pickup Particle Entity

This entity defines the visual and auditory effects when a gold pickup is collected in Noita. It primarily uses `SpriteParticleEmitterComponent` to generate various particle effects and a `LightComponent` for a visual glow.

## Key Components

### `VelocityComponent`

Controls the movement and physics of the particles.

*   `gravity_y`: Set to `0`, meaning particles are not affected by gravity.
*   `air_friction`: Set to `4.0`, indicating moderate air resistance.

### `SimplePhysicsComponent`

A basic physics component, likely for simple interactions or collision handling if needed.

### `LifetimeComponent`

Determines how long the entity (and its associated particles) persists.

*   `lifetime`: Set to `6` seconds.

### `SpriteParticleEmitterComponent` (Multiple Instances)

These components are responsible for emitting different types of particles.

#### Emitter 1 (Primary Shine)

*   `sprite_file`: `data/particles/shine_08.xml` - The visual sprite for these particles.
*   `lifetime`: `0.1` to `0.5` seconds (randomized).
*   `emission_interval_min_frames`/`max_frames`: `1` - Particles are emitted continuously.
*   `count_min`/`max`: `1` - Emits one particle at a time.
*   `additive`: `1` - Particles are added to the scene, creating a brighter effect.
*   `emissive`: `0` - Particles do not emit light themselves.
*   `scale`: `1.0` x `1.0`, with slight randomization (`-0.1` to `0.1`).
*   `sprite_random_rotation`: `1` - Sprites can have random rotations.
*   `randomize_velocity`: Particles are given a significant random velocity in X and Y directions (`-50` to `50`).
*   `randomize_position`: Small random offset in position (`-1` to `1`).
*   `velocity_slowdown`: `6` - Particles gradually slow down.
*   `randomize_animation_speed_coeff`: `0.667` to `1.0` - Controls the animation speed of the sprites.

#### Emitter 2 (Larger Glow)

*   `sprite_file`: `data/particles/shine_06.xml` - A different sprite for a larger glow effect.
*   `lifetime`: `0.56` seconds.
*   `emission_interval_min_frames`/`max_frames`: `99999999` - Emitted only once at the start.
*   `additive`: `1` - Additive blending.
*   `emissive`: `1` - These particles contribute to the light.
*   `scale`: `1.0` x `1.0`, with slight randomization (`-0.1` to `0.1`).
*   `count_min`/`max`: `1` - Emits one particle.
*   `sprite_random_rotation`: `1` - Random sprite rotation.
*   `randomize_velocity`: Moderate random velocity (`-10` to `10`).
*   `randomize_position`: Larger random offset (`-2` to `2`).
*   `randomize_animation_speed_coeff`: `0.667` to `1.0`.

#### Emitter 3 (Fading Sparkles - Disabled by default)

*   `_enabled`: `0` - This emitter is currently disabled.
*   `sprite_file`: `data/particles/shine_05.xml`.
*   `lifetime`: `0.2` seconds.
*   `color`: White (`r="1" g="1" b="1" a="1"`).
*   `color_change`: Alpha decreases (`a="-1"`).
*   `emission_interval_min_frames`/`max_frames`: `1` - Continuous emission.
*   `additive`: `1`.
*   `emissive`: `0`.
*   `scale`: `1.0` x `1.0`, with slight randomization.
*   `count_min`/`max`: `1` to `2` - Emits 1 or 2 particles.
*   `sprite_random_rotation`: `1`.
*   `randomize_velocity`: Significant random velocity (`-30` to `30`).
*   `randomize_position`: Larger random offset (`-4` to `4`).
*   `randomize_animation_speed_coeff`: `0.667` to `1.0`.

### `LightComponent`

Adds a dynamic light source to the entity.

*   `_enabled`: `1` - The light is active.
*   `r`, `g`, `b`: `228`, `255`, `70` - A yellowish-green color.
*   `radius`: `48` - The range of the light.
*   `fade_out_time`: `2` seconds - How long the light takes to fade.

### `AudioComponent`

Plays a sound effect when the entity is active.

*   `file`: `data/audio/Desktop/event_cues.bank` - The audio bank containing the sound.
*   `event_root`: `event_cues/goldnugget` - The specific audio event to trigger.