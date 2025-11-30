---
title: Explosion Smoke Pillar Top Right Particle
category: entities
---

# Explosion Smoke Pillar Top Right Particle

This document describes the `explosion_smoke_pillar_top_right.xml` entity, which is used to generate smoke particles for explosions in Noita.

## Key Components

### VelocityComponent

Controls the movement and physics of the particle.

*   `gravity_y="0"`: The particle is not affected by gravity.
*   `air_friction="7.0"`: A moderate amount of air friction is applied.

### SimplePhysicsComponent

Enables basic physics interactions for the particle.

### SetStartVelocityComponent

Defines the initial velocity of the emitted particles.

*   `randomize_speed.min="120"`: Minimum initial speed.
*   `randomize_speed.max="140"`: Maximum initial speed.
*   `randomize_angle.min="-0.2"`: Minimum initial angle (radians).
*   `randomize_angle.max="0.0"`: Maximum initial angle (radians). This suggests a slight upward or horizontal initial direction.

### DieIfSpeedBelowComponent

Determines when the particle should be destroyed.

*   `min_speed="50"`: The particle will be removed if its speed drops below 50.

### SpriteParticleEmitterComponent

This is the core component responsible for emitting the smoke particles.

*   `sprite_file="data/particles/smoke_cloud_tiny_$[1-4].xml"`: Specifies the sprite files to be used for the smoke particles. The `$[1-4]` indicates that one of four variations of `smoke_cloud_tiny` will be randomly chosen.
*   `emission_interval_min_frames="4"`: Minimum frames between particle emissions.
*   `emission_interval_max_frames="4"`: Maximum frames between particle emissions. This means particles are emitted at a consistent rate.
*   `additive="1"`: The particle's color will be added to the background, creating a glowing effect.
*   `emissive="0"`: The particle itself does not emit light.
*   `scale.x="1.0"`, `scale.y="1.0"`: Default scale of the emitted particles.
*   `sprite_random_rotation="1"`: The sprite will have a random rotation.
*   `randomize_scale.min_x="-0.1"`, `randomize_scale.max_x="0.1"`: Random variation in X-axis scale.
*   `randomize_scale.min_y="-0.1"`, `randomize_scale.max_y="0.1"`: Random variation in Y-axis scale.
*   `randomize_velocity.min_y="-10"`, `randomize_velocity.max_y="0"`: Random variation in Y-axis velocity, pushing particles slightly upwards.
*   `randomize_velocity.min_x="5"`, `randomize_velocity.max_x="10"`: Random variation in X-axis velocity, pushing particles to the right.
*   `randomize_position.min_y="-5"`, `randomize_position.max_y="5"`: Random variation in Y-axis position relative to the emitter.
*   `randomize_position.min_x="-5"`, `randomize_position.max_x="5"`: Random variation in X-axis position relative to the emitter.
*   `randomize_animation_speed_coeff.min="0.667"`, `randomize_animation_speed_coeff.max="1.5"`: Random variation in the animation speed of the sprite.
*   `render_back="1"`: The particle will be rendered behind other elements.

```xml
<Entity>

    <VelocityComponent
        gravity_y="0"
        air_friction="7.0" >
    </VelocityComponent>

    <SimplePhysicsComponent>
    </SimplePhysicsComponent>

    <SetStartVelocityComponent
        randomize_speed.min="120"
        randomize_speed.max="140"
        randomize_angle.min="-0.2"
        randomize_angle.max="0.0" >
    </SetStartVelocityComponent>

    <DieIfSpeedBelowComponent
        min_speed="50" 
		>
    </DieIfSpeedBelowComponent>

    <SpriteParticleEmitterComponent
        sprite_file="data/particles/smoke_cloud_tiny_$[1-4].xml"
        emission_interval_min_frames="4"
        emission_interval_max_frames="4"
        additive="1"
        emissive="0"
        scale.x="1.0"
        scale.y="1.0"
        sprite_random_rotation="1"
        randomize_scale.min_x="-0.1" 
        randomize_scale.max_x="0.1" 
        randomize_scale.min_y="-0.1" 
        randomize_scale.max_y="0.1" 
        randomize_velocity.min_y="-10" 
        randomize_velocity.max_y="0"
        randomize_velocity.min_x="5"  
        randomize_velocity.max_x="10"
		randomize_position.min_y="-5" 
        randomize_position.max_y="5"
        randomize_position.min_x="-5"  
        randomize_position.max_x="5"
        randomize_animation_speed_coeff.min="0.667"  
        randomize_animation_speed_coeff.max="1.5"
        render_back="1" >
    </SpriteParticleEmitterComponent>

</Entity>
```