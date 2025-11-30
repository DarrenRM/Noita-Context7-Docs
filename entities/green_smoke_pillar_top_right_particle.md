---
title: Green Smoke Pillar Top Right Particle
category: entities
---

# Green Smoke Pillar Top Right Particle

This entity defines a particle effect that creates a pillar of green smoke, primarily moving upwards and to the right. It's designed to be used in explosion effects.

## Key Components

### VelocityComponent
Controls the particle's movement physics.

*   `gravity_y="0"`: The particle is not affected by gravity.
*   `air_friction="7.0"`: Significant air friction slows the particle down.

### SimplePhysicsComponent
Indicates that the particle has basic physics properties.

### SetStartVelocityComponent
Determines the initial velocity of the particle.

*   `randomize_speed.min="120"`: Minimum initial speed.
*   `randomize_speed.max="140"`: Maximum initial speed.
*   `randomize_angle.min="-0.2"`: Minimum initial angle (radians).
*   `randomize_angle.max="0.0"`: Maximum initial angle (radians), favoring a slight upward and rightward direction.

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   `min_speed="50"`: The particle will disappear if its speed drops below 50.

### SpriteParticleEmitterComponent
This is the core component responsible for emitting the visual smoke particles.

*   `sprite_file="data/particles/smoke_cloud_tiny_green_$[1-4].xml"`: Specifies the sprite files to be used for the smoke. It randomly selects from `smoke_cloud_tiny_green_1.xml` to `smoke_cloud_tiny_green_4.xml`.
*   `emission_interval_min_frames="4"`: Minimum frames between particle emissions.
*   `emission_interval_max_frames="4"`: Maximum frames between particle emissions.
*   `additive="1"`: Particles are rendered additively, meaning they contribute to the brightness of what's behind them.
*   `emissive="0"`: The particles themselves do not emit light.
*   `scale.x="1.0"`, `scale.y="1.0"`: Base scale of the particles.
*   `sprite_random_rotation="1"`: The sprite will have a random rotation.
*   `randomize_scale.min_x="-0.1"`, `randomize_scale.max_x="0.1"`: Random variation in X-axis scale.
*   `randomize_scale.min_y="-0.1"`, `randomize_scale.max_y="0.1"`: Random variation in Y-axis scale.
*   `randomize_velocity.min_y="-10"`, `randomize_velocity.max_y="0"`: Random variation in Y-axis velocity, generally pushing particles upwards.
*   `randomize_velocity.min_x="5"`, `randomize_velocity.max_x="10"`: Random variation in X-axis velocity, pushing particles to the right.
*   `randomize_position.min_y="-5"`, `randomize_position.max_y="5"`: Random variation in the emission position on the Y-axis.
*   `randomize_position.min_x="-5"`, `randomize_position.max_x="5"`: Random variation in the emission position on the X-axis.
*   `randomize_animation_speed_coeff.min="0.667"`, `randomize_animation_speed_coeff.max="1.5"`: Random variation in the animation speed of the smoke sprites.
*   `render_back="1"`: Particles are rendered behind other elements.

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
        sprite_file="data/particles/smoke_cloud_tiny_green_$[1-4].xml"
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