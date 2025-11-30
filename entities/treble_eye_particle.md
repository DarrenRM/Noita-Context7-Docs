---
title: Treble Eye Particle
category: entities
---

# Treble Eye Particle

This document describes the `treble_eye.xml` entity, which defines a particle effect in Noita.

## Entity Definition

The `treble_eye.xml` entity is a particle effect with specific visual and auditory properties.

### Key Components

*   **`InheritTransformComponent`**:
    *   `Transform`: Defines the initial position of the particle.
        *   `position.x`: 0
        *   `position.y`: -10 (relative to its parent or spawn point)

*   **`SpriteComponent`**: Controls the visual appearance of the particle.
    *   `alpha`: 0.55 (transparency level)
    *   `image_file`: `data/particles/treble_eye.xml` (references its own definition for sprite data)
    *   `smooth_filtering`: 0 (disables smooth filtering for a sharper look)
    *   `kill_entity_after_finished`: 1 (the particle will be removed once its animation/effect is complete)
    *   `fog_of_war_hole`: 0 (does not create a hole in the fog of war)
    *   `additive`: 1 (uses additive blending for rendering, making it appear brighter when overlapping)

*   **`AudioComponent`**: Defines the sound associated with this particle.
    *   `file`: `data/audio/Desktop/event_cues.bank` (the audio bank containing the sound event)
    *   `event_root`: `event_cues/treble_eye` (the specific sound event to trigger)

```xml
<Entity>
    <InheritTransformComponent>
        <Transform 
            position.x="0"
            position.y="-10" 
        ></Transform>
    </InheritTransformComponent>    
    
    <SpriteComponent 
        alpha="0.55"
        image_file="data/particles/treble_eye.xml"
        smooth_filtering="0"
        kill_entity_after_finished="1"
        fog_of_war_hole="0"
        additive="1" >
    </SpriteComponent>

    <AudioComponent
        file="data/audio/Desktop/event_cues.bank"
        event_root="event_cues/treble_eye" >
    </AudioComponent>

</Entity>
```