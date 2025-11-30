---
title: Red Smoke Pillar Top Right Particle
category: entities
---

# Red Smoke Pillar Top Right Particle

This entity defines a particle effect that generates a pillar of red smoke, primarily moving upwards and slightly to the right. It's designed to be used in explosion effects.

## Key Components

### VelocityComponent
Controls the particle's movement and how it interacts with the environment.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
*   `air_friction="7.0"`: Applies significant air friction, slowing the particle down over time.

### SimplePhysicsComponent
Enables basic physics interactions for the particle.

### SetStartVelocityComponent
Determines the initial velocity of the particle upon creation.

*   `randomize_speed.min="120"`: Minimum initial speed.
*   `randomize_speed.max="140"`: Maximum initial speed.
*   `randomize_angle.min="-0.2"`: Minimum initial angle (radians).
*   `randomize_angle.max="0.0"`: Maximum initial angle (radians). This biases the particle towards moving slightly upwards and to the right.

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   `min_speed="50"`: The particle will be removed if its speed drops below 50.

### SpriteParticleEmitterComponent
This is the core component responsible for emitting and rendering the smoke particles.

*   `sprite_file="data/particles/smoke_cloud_tiny_red_$[1-4].xml"`: Specifies the sprite files to be used for the particles. The `$[1-4]` indicates that one of four variations of `smoke_cloud_tiny_red` will be randomly chosen.
*   `emission_interval_min_frames="4"`: Minimum frames between particle emissions.
*   `emission_interval_max_frames="4"`: Maximum frames between particle emissions. This results in consistent emission.
*   `additive="1"`: Particles are rendered additively, meaning their colors are added to what's behind them, creating a glowing effect.
*   `emissive="0"`: Particles are not emissive (they don't emit light themselves).
*   `scale.x="1.0"`, `scale.y="1.0"`: Base scale of the particles.
*   `sprite_random_rotation="1"`: Randomizes the rotation of each emitted sprite.
*   `randomize_scale.min_x="-0.1"`, `randomize_scale.max_x="0.1"`: Randomizes the x-scale of particles slightly.
*   `randomize_scale.min_y="-0.1"`, `randomize_scale.max_y="0.1"`: Randomizes the y-scale of particles slightly.
*   `randomize_velocity.min_y="-10"`, `randomize_velocity.max_y="0"`: Randomizes the vertical velocity of emitted particles, pushing them slightly upwards.
*   `randomize_velocity.min_x="5"`, `randomize_velocity.max_x="10"`: Randomizes the horizontal velocity of emitted particles, pushing them to the right.
*   `randomize_position.min_y="-5"`, `randomize_position.max_y="5"`: Randomizes the emission position slightly on the y-axis.
*   `randomize_position.min_x="-5"`, `randomize_position.max_x="5"`: Randomizes the emission position slightly on the x-axis.
*   `randomize_animation_speed_coeff.min="0.667"`, `randomize_animation_speed_coeff.max="1.5"`: Randomizes the animation speed of the particle sprites.
*   `render_back="1"`: Renders these particles behind other elements.

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
        sprite_file="data/particles/smoke_cloud_tiny_red_$[1-4].xml"
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
		render_back="1"
		>
    </SpriteParticleEmitterComponent>

</Entity>
```