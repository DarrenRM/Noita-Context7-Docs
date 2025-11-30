---
title: Green Large Smoke Pillar Particle
category: entities
---

# Green Large Smoke Pillar Particle

This entity defines a large green smoke pillar particle effect, typically used in explosions. It utilizes a `SpriteParticleEmitterComponent` to generate multiple smoke sprites with randomized properties and `LoadEntitiesComponent` to spawn additional, more specific smoke entities at different times.

## Key Components and Attributes

### VelocityComponent
Controls the particle's movement and interaction with the environment.

*   **gravity\_y**: `0` - The particle is not affected by gravity.
*   **air\_friction**: `4.0` - A moderate amount of air friction is applied.

### SimplePhysicsComponent
Indicates that the entity has basic physics properties.

### SetStartVelocityComponent
Determines the initial velocity of the particles.

*   **randomize\_speed.min**: `50` - Minimum initial speed.
*   **randomize\_speed.max**: `60` - Maximum initial speed.
*   **randomize\_angle.min**: `-1.57` - Minimum initial angle (in radians).
*   **randomize\_angle.max**: `-1.57` - Maximum initial angle (in radians). This fixed angle suggests a specific directional emission.

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   **min\_speed**: `20` - The particle will be removed if its speed drops below this value.

### SpriteParticleEmitterComponent
The core component responsible for emitting smoke particles.

*   **sprite\_file**: `data/particles/smoke_cloud_green_$[1-4].xml` - Specifies the sprite files to be used, with a range `$[1-4]` indicating variation.
*   **emission\_interval\_min\_frames**: `1` - Minimum frames between emissions.
*   **emission\_interval\_max\_frames**: `2` - Maximum frames between emissions.
*   **additive**: `1` - Particles are rendered additively, meaning their colors are added to the background.
*   **emissive**: `0` - Particles are not emissive (do not emit light).
*   **scale.x / scale.y**: `1.0` - Base scale of the particles.
*   **count\_min / count\_max**: `1` to `2` - Number of particles emitted per interval.
*   **sprite\_random\_rotation**: `1` - Sprites will have random rotation.
*   **randomize\_scale.min\_x / max\_x**: `-0.1` to `0.1` - Randomizes the X scale of emitted particles.
*   **randomize\_scale.min\_y / max\_y**: `-0.1` to `0.1` - Randomizes the Y scale of emitted particles.
*   **randomize\_velocity.min\_x / max\_x**: `-10` to `10` - Randomizes the X velocity of emitted particles.
*   **randomize\_velocity.min\_y / max\_y**: `-10` to `10` - Randomizes the Y velocity of emitted particles.
*   **randomize\_position.min\_x / max\_x**: `-10` to `10` - Randomizes the emission position within this range.
*   **randomize\_position.min\_y / max\_y**: `-10` to `10` - Randomizes the emission position within this range.
*   **randomize\_animation\_speed\_coeff.min / max**: `0.667` to `1.0` - Randomizes the animation speed coefficient of the sprites.
*   **velocity\_always\_away\_from\_center**: `1` - Particles are always emitted away from the center of the emitter.
*   **render\_back**: `1` - Particles are rendered behind other elements.

### LoadEntitiesComponent
Used to load other entities after a delay, creating a layered effect.

*   **count.min / max**: `1` - Spawns one entity.
*   **entity\_file**: Specifies the entity to load (e.g., `explosion_smoke_pillar_top_left_green.xml`).
*   **kill\_entity**: `0` - The parent entity is not killed after loading.
*   **timeout\_frames**: The delay in frames before the entity is loaded.

This component is used multiple times with different `entity_file` and `timeout_frames` to create a dynamic smoke pillar that evolves over time.

```xml
<Entity>

    <VelocityComponent
        gravity_y="0"
        air_friction="4.0" >
    </VelocityComponent>

    <SimplePhysicsComponent>
    </SimplePhysicsComponent>

    <SetStartVelocityComponent
        randomize_speed.min="50"
        randomize_speed.max="60"
        randomize_angle.min="-1.57"
        randomize_angle.max="-1.57" >
    </SetStartVelocityComponent>

    <DieIfSpeedBelowComponent
        min_speed="20" >
    </DieIfSpeedBelowComponent>

    <SpriteParticleEmitterComponent
        sprite_file="data/particles/smoke_cloud_green_$[1-4].xml"
        emission_interval_min_frames="1"
        emission_interval_max_frames="2"
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
        randomize_velocity.min_y="-10" 
        randomize_velocity.max_y="10"
        randomize_velocity.min_x="-10" 	
        randomize_velocity.max_x="10"
		randomize_position.min_y="-10" 
        randomize_position.max_y="10"
        randomize_position.min_x="-10"  
        randomize_position.max_x="10"
        randomize_animation_speed_coeff.min="0.667"  
        randomize_animation_speed_coeff.max="1.0" 
		velocity_always_away_from_center="1"
		render_back="1"
		>
    </SpriteParticleEmitterComponent>

    <LoadEntitiesComponent
        count.min="1"
        count.max="1"
        entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_left_green.xml"
        kill_entity="0"
        timeout_frames="10" >
    </LoadEntitiesComponent>

    <LoadEntitiesComponent
        count.min="1"
        count.max="1"
        entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_right_green.xml"
        kill_entity="0"
        timeout_frames="10" >
    </LoadEntitiesComponent>

    <LoadEntitiesComponent
        count.min="1"
        count.max="1"
        entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_left_green.xml"
        kill_entity="0"
        timeout_frames="12" >
    </LoadEntitiesComponent>

    <LoadEntitiesComponent
        count.min="1"
        count.max="1"
        entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_right_green.xml"
        kill_entity="0"
        timeout_frames="12" >
    </LoadEntitiesComponent>
</Entity>
```