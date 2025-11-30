---
title: Berserk Particle Emitter
category: entities
---

# Berserk Particle Emitter

This document describes the configuration for a particle emitter that generates "berserk" particles in Noita. These particles are visually characterized by a fading alpha and a subtle light effect.

## SpriteParticleEmitterComponent

This component defines the behavior and appearance of the particles being emitted.

### Key Attributes:

*   **`sprite_file`**: Specifies the sprite texture to be used for the particles. In this case, it uses a sequence of sprites named `berserk_01.xml` through `berserk_04.xml`.
*   **`lifetime`**: The duration each particle exists in seconds. Set to `1.5` seconds.
*   **`color.a`**: The initial alpha transparency of the particles. Set to `1` (fully opaque).
*   **`color_change.a`**: The rate at which the alpha transparency changes over the particle's lifetime. A value of `-0.5` means the particles fade out.
*   **`gravity.y`**: The gravitational pull affecting the particles along the Y-axis. Set to `10`.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the timing between particle emissions. Particles are emitted every `1` to `3` frames.
*   **`count_min` / `count_max`**: The number of particles emitted per emission event. Set to `1` particle.
*   **`randomize_position`**: Defines the random offset from the emitter's origin for each particle's spawn point.
    *   `min_x="-5"`, `max_x="5"`: Horizontal spread.
    *   `min_y="-10"`, `max_y="0"`: Vertical spread.
*   **`randomize_velocity`**: Defines the random initial velocity applied to each particle.
    *   `min_x="-10"`, `max_x="10"`: Horizontal velocity range.
    *   `min_y="-20"`, `max_y="5"`: Vertical velocity range.

### Other Notable Attributes:

*   `delay`: `0` (particles start emitting immediately).
*   `color.r`, `color.g`, `color.b`: Initial RGB color values (all `1`, indicating white).
*   `color_change.r`, `color_change.g`, `color_change.b`: No change in RGB color.
*   `velocity.x`, `velocity.y`: Base velocity (both `0`).
*   `velocity_slowdown`: `0` (no slowdown applied).
*   `rotation`, `angular_velocity`: No initial rotation or angular velocity.
*   `use_velocity_as_rotation`: `0` (velocity does not influence rotation).
*   `scale.x`, `scale.y`: Initial scale (both `1`).
*   `scale_velocity.x`, `scale_velocity.y`: No change in scale over time.
*   `randomize_rotation.min` / `randomize_rotation.max`: Random initial rotation applied to particles.

## LightComponent

This component adds a light source to the entity, affecting the surrounding environment.

### Key Attributes:

*   **`_enabled`**: `1` (the light component is active).
*   **`radius`**: The range of the light effect. Set to `60`.
*   **`r`**, **`g`**, **`b`**: The RGB color of the light. Set to `0`, `40`, `80`, creating a dark blue hue.

```xml
<Entity>
  <SpriteParticleEmitterComponent
    sprite_file="data/particles/berserk_0$[1-4].xml"
    delay="0"
    lifetime="1.5"
    color.r="1" color.g="1" color.b="1" color.a="1"
    color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-0.5"
    velocity.x="0" velocity.y="0"
    gravity.x="0" gravity.y="10"
    velocity_slowdown="0"
    rotation="0"
    angular_velocity="0"
    use_velocity_as_rotation="0"
    scale.x="1" scale.y="1"
    scale_velocity.x="0" scale_velocity.y="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="3"
    count_min="1" count_max="1"
    randomize_rotation.min="-0.3415"
    randomize_rotation.max="0.3415"
    randomize_position.min_x="-5"
    randomize_position.max_x="5"
    randomize_position.min_y="-10"
    randomize_position.max_y="0"
	randomize_velocity.min_x="-10"
	randomize_velocity.max_x="10"
	randomize_velocity.min_y="-20"
	randomize_velocity.max_y="5"
    >
  </SpriteParticleEmitterComponent>
  
  <LightComponent 
    _enabled="1" 
    radius="60" 
	r="0"
	g="40"
	b="80">
  </LightComponent>
</Entity>
```