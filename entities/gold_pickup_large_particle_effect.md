---
title: Gold Pickup Large Particle Effect
category: entities
---

# Gold Pickup Large Particle Effect

This entity defines the visual and auditory effects when a large gold pickup is collected in Noita. It utilizes multiple `SpriteParticleEmitterComponent` instances to create a shimmering, dissipating effect with varying sprites, scales, and velocities.

## Key Components

### `VelocityComponent`

Controls the basic physics of the particles.

| Attribute      | Value | Description                                  |
|----------------|-------|----------------------------------------------|
| `gravity_y`    | `0`   | No vertical gravity applied to the particles. |
| `air_friction` | `4.0` | Moderate air friction slows particles down.  |

### `SimplePhysicsComponent`

A basic physics component, likely for simple interactions.

### `LifetimeComponent`

Determines how long the entire entity (and its particles) persists.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `lifetime`| `6`   | The entity lasts for 6 seconds.           |

### `SpriteParticleEmitterComponent`

This is the core component responsible for generating particles. This entity uses multiple instances to layer different visual effects.

#### Emitter 1 (Main Shine)

*   **`sprite_file`**: `data/particles/shine_08.xml`
*   **`lifetime`**: `0.1` (short-lived particles)
*   **`randomize_lifetime`**: `0.1` to `0.3` (slight variation in particle lifespan)
*   **`emission_interval_min_frames` / `max_frames`**: `1` (emits continuously)
*   **`count_min` / `count_max`**: `1` (emits one particle at a time)
*   **`additive`**: `1` (particles are added to the scene, making them brighter)
*   **`sprite_random_rotation`**: `1` (particles can have random rotations)
*   **`randomize_scale`**: Small variations in X and Y scale (`-0.1` to `0.1`).
*   **`randomize_velocity`**: Significant random velocity in X and Y (`-80` to `80`), creating an outward burst.
*   **`randomize_position`**: Small positional offset (`-2` to `2`) for particle origin.
*   **`velocity_slowdown`**: `6` (particles gradually slow down).

#### Emitter 2 (Secondary Shine)

*   **`sprite_file`**: `data/particles/shine_07.xml`
*   **`lifetime`**: `0.3`
*   **`delay`**: `0.4` (starts emitting after a short delay)
*   **`emission_interval_min_frames` / `max_frames`**: `99999999` (emits only once at the start)
*   **`count_min` / `count_max`**: `1` to `3`
*   **`randomize_velocity`**: Moderate random velocity (`-10` to `10`).
*   **`randomize_position`**: Wider positional offset (`-4` to `4`).

#### Emitter 3 (Emissive Glow)

*   **`sprite_file`**: `data/particles/shine_06.xml`
*   **`lifetime`**: `0.56`
*   **`emission_interval_min_frames` / `max_frames`**: `99999999` (emits only once)
*   **`emissive`**: `1` (particles emit light themselves)
*   **`count_min` / `count_max`**: `2` to `5`
*   **`randomize_velocity`**: Moderate random velocity (`-10` to `10`).
*   **`randomize_position`**: Wider positional offset (`-4` to `4`).

#### Emitter 4 (Fading Sparkle - Disabled)

*   **`_enabled`**: `0` (This emitter is currently disabled)
*   **`sprite_file`**: `data/particles/shine_05.xml`
*   **`lifetime`**: `0.2`
*   **`color`**: White (`r="1" g="1" b="1" a="1"`)
*   **`color_change`**: Alpha fades out (`a="-1"`).
*   **`randomize_velocity`**: Higher random velocity (`-30` to `30`).
*   **`randomize_position`**: Wider positional offset (`-4` to `4`).

### `LightComponent`

Adds a light source to the entity.

| Attribute       | Value | Description                               |
|-----------------|-------|-------------------------------------------|
| `_enabled`      | `1`   | The light is active.                      |
| `r`, `g`, `b`   | `228`, `255`, `70` | Golden yellow color.                      |
| `radius`        | `48`  | The radius of the light.                  |
| `fade_out_time` | `2`   | The light fades out over 2 seconds.       |

### `AudioComponent`

Plays a sound effect when the entity is active.

*   **`file`**: `data/audio/Desktop/event_cues.bank`
*   **`event_root`**: `event_cues/goldnugget` (Triggers the "goldnugget" sound event).

```xml
<Entity>

    <VelocityComponent
        gravity_y="0"
        air_friction="4.0" >
    </VelocityComponent>

    <SimplePhysicsComponent>
    </SimplePhysicsComponent>

    <LifetimeComponent
		lifetime="6"
		>
	</LifetimeComponent>

    <SpriteParticleEmitterComponent
        sprite_file="data/particles/shine_08.xml"
        lifetime="0.1"
        randomize_lifetime.min="0.1"
        randomize_lifetime.max="0.3"
        emission_interval_min_frames="1"
        emission_interval_max_frames="1"
        count_min="1"
        count_max="1"
        additive="1"
        emissive="0"
        scale.x="1.0"
        scale.y="1.0"
        sprite_random_rotation="1"
        randomize_scale.min_x="-0.1" 
        randomize_scale.max_x="0.1" 
        randomize_scale.min_y="-0.1" 
        randomize_scale.max_y="0.1" 
        randomize_velocity.min_y="-80" 
        randomize_velocity.max_y="80"
        randomize_velocity.min_x="-80"  
        randomize_velocity.max_x="80"
        randomize_position.min_y="-2" 
        randomize_position.max_y="2"
        randomize_position.min_x="-2"  
        randomize_position.max_x="2"
        velocity_slowdown="6"
        randomize_animation_speed_coeff.min="0.667"  
        randomize_animation_speed_coeff.max="1.0" 
        >
    </SpriteParticleEmitterComponent>

    <SpriteParticleEmitterComponent
        sprite_file="data/particles/shine_07.xml"
        lifetime="0.3"
        delay="0.4"
        emission_interval_min_frames="99999999"
        emission_interval_max_frames="99999999"
        additive="1"
        emissive="0"
        scale.x="1.0"
        scale.y="1.0"
        count_min="1"
        count_max="3"
        sprite_random_rotation="1"
        randomize_scale.min_x="-0.1" 
        randomize_scale.max_x="0.1" 
        randomize_scale.min_y="-0.1" 
        randomize_scale.max_y="0.1" 
        randomize_velocity.min_y="-10" 
        randomize_velocity.max_y="10"
        randomize_velocity.min_x="-10"  
        randomize_velocity.max_x="10"
        randomize_position.min_y="-4" 
        randomize_position.max_y="4"
        randomize_position.min_x="-4"  
        randomize_position.max_x="4"
        randomize_animation_speed_coeff.min="0.667"  
        randomize_animation_speed_coeff.max="1.0" 
        >
    </SpriteParticleEmitterComponent>

    <SpriteParticleEmitterComponent
        sprite_file="data/particles/shine_06.xml"
        lifetime="0.56"
        emission_interval_min_frames="99999999"
        emission_interval_max_frames="99999999"
        additive="1"
        emissive="1"
        scale.x="1.0"
        scale.y="1.0"
        count_min="2"
        count_max="5"
        sprite_random_rotation="1"
        randomize_scale.min_x="-0.1" 
        randomize_scale.max_x="0.1" 
        randomize_scale.min_y="-0.1" 
        randomize_scale.max_y="0.1" 
        randomize_velocity.min_y="-10" 
        randomize_velocity.max_y="10"
        randomize_velocity.min_x="-10"  
        randomize_velocity.max_x="10"
        randomize_position.min_y="-4" 
        randomize_position.max_y="4"
        randomize_position.min_x="-4"  
        randomize_position.max_x="4"
        randomize_animation_speed_coeff.min="0.667"  
        randomize_animation_speed_coeff.max="1.0" 
        >
    </SpriteParticleEmitterComponent>

    <SpriteParticleEmitterComponent
        _enabled="0"
        sprite_file="data/particles/shine_05.xml"
		lifetime="0.2"
		color.r="1" color.g="1" color.b="1" color.a="1"
		color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-1"
        emission_interval_min_frames="1"
        emission_interval_max_frames="1"
        additive="1"
        emissive="0"
        scale.x="1.0"
        scale.y="1.0"
		count_min="1"
		count_max="2"
        sprite_random_rotation="1"
        randomize_scale.min_x="-0.1" 
        randomize_scale.max_x="0.1" 
        randomize_scale.min_y="-0.1" 
        randomize_scale.max_y="0.1" 
        randomize_velocity.min_y="-30" 
        randomize_velocity.max_y="30"
        randomize_velocity.min_x="-30" 	
        randomize_velocity.max_x="30"
		randomize_position.min_y="-4" 
        randomize_position.max_y="4"
        randomize_position.min_x="-4"  
        randomize_position.max_x="4"
        randomize_animation_speed_coeff.min="0.667"  
        randomize_animation_speed_coeff.max="1.0" 
		>
    </SpriteParticleEmitterComponent>
	
	<LightComponent 
		_enabled="1" 
		r="228"
		g="255"
		b="70"
		radius="48" 
		fade_out_time="2"
		>
	</LightComponent>

    <AudioComponent
      file="data/audio/Desktop/event_cues.bank"
      event_root="event_cues/goldnugget">
    </AudioComponent>
  
</Entity>
```