---
title: Gold Pickup Huge Particle Effect
category: entities
---

# Gold Pickup Huge Particle Effect

This entity defines the visual and auditory effects for a large gold pickup in Noita. It utilizes multiple `SpriteParticleEmitterComponent` instances to create a layered particle effect, accompanied by a `LightComponent` for a glowing effect and an `AudioComponent` for sound.

## Key Components

### `VelocityComponent`

Controls the basic physics of the particles.

| Attribute      | Value   | Description                               |
|----------------|---------|-------------------------------------------|
| `gravity_y`    | `0`     | No vertical gravity applied to particles. |
| `air_friction` | `4.0`   | Moderate air friction.                    |

### `SimplePhysicsComponent`

Enables basic physics interactions for the entity.

### `LifetimeComponent`

Determines how long the entity (and its particles) will exist.

| Attribute | Value | Description             |
|-----------|-------|-------------------------|
| `lifetime`| `6`   | The entity lasts for 6 seconds. |

### `SpriteParticleEmitterComponent` (Multiple Instances)

These components are responsible for generating and managing the visual particles. Each instance uses a different sprite and has unique emission parameters to create a complex effect.

#### Instance 1: Main Sparkles

*   **`sprite_file`**: `data/particles/shine_08.xml`
*   **`lifetime`**: `0.1` (short-lived particles)
*   **`randomize_lifetime`**: `0.1` to `0.7` (varied particle lifespan)
*   **`emission_interval_min_frames` / `max_frames`**: `1` (emits frequently)
*   **`count_min` / `count_max`**: `1` to `3` (small bursts)
*   **`additive`**: `1` (particles are added to the scene, making them brighter)
*   **`emissive`**: `0` (particles don't emit light themselves)
*   **`scale`**: `1.0` (default size)
*   **`sprite_random_rotation`**: `1` (particles can rotate randomly)
*   **`randomize_scale`**: Small variations in X and Y scale (`-0.1` to `0.1`).
*   **`randomize_velocity`**: Significant random velocity in X and Y (`-150` to `150`).
*   **`randomize_position`**: Small random offset from the origin (`-2` to `2`).
*   **`velocity_slowdown`**: `7` (particles slow down over time).
*   **`randomize_animation_speed_coeff`**: `0.667` to `1.0` (varied animation speed).

#### Instance 2: Larger, Slower Particles

*   **`sprite_file`**: `data/particles/shine_07.xml`
*   **`lifetime`**: `0.3`
*   **`delay`**: `0.4` (starts emitting after a short delay)
*   **`emission_interval_min_frames` / `max_frames`**: `99999999` (emits only once at the start)
*   **`count_min` / `count_max`**: `5` to `10`
*   **`additive`**: `1`
*   **`emissive`**: `0`
*   **`scale`**: `1.0`
*   **`sprite_random_rotation`**: `1`
*   **`randomize_scale`**: Small variations in X and Y scale (`-0.1` to `0.1`).
*   **`randomize_velocity`**: Moderate random velocity in X and Y (`-10` to `10`).
*   **`randomize_position`**: Larger random offset from the origin (`-10` to `10`).
*   **`randomize_animation_speed_coeff`**: `0.667` to `1.0`.

#### Instance 3: Emissive Glow Particles

*   **`sprite_file`**: `data/particles/shine_06.xml`
*   **`lifetime`**: `0.56`
*   **`emission_interval_min_frames` / `max_frames`**: `99999999` (emits only once at the start)
*   **`additive`**: `1`
*   **`emissive`**: `1` (these particles emit light)
*   **`count_min` / `count_max`**: `4` to `8`
*   **`scale`**: `1.0`
*   **`sprite_random_rotation`**: `1`
*   **`randomize_scale`**: Small variations in X and Y scale (`-0.1` to `0.1`).
*   **`randomize_velocity`**: Moderate random velocity in X and Y (`-10` to `10`).
*   **`randomize_position`**: Largest random offset from the origin (`-12` to `12`).
*   **`randomize_animation_speed_coeff`**: `0.667` to `1.0`.

### `LightComponent`

Adds a dynamic light source to the entity.

| Attribute      | Value   | Description                               |
|----------------|---------|-------------------------------------------|
| `_enabled`     | `1`     | Light is enabled.                         |
| `r`, `g`, `b`  | `228`, `255`, `70` | Golden yellow color.                  |
| `radius`       | `48`    | The radius of the light.                  |
| `fade_out_time`| `4`     | The light fades out over 4 seconds.       |

### `AudioComponent`

Plays a sound effect when the entity is active.

| Attribute   | Value                               | Description                               |
|-------------|-------------------------------------|-------------------------------------------|
| `file`      | `data/audio/Desktop/event_cues.bank`| The audio bank containing the event.      |
| `event_root`| `event_cues/goldnugget`             | The specific sound event to trigger.      |