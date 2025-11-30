---
title: Teleport Bunker Back Entity
category: entities
---

# Teleport Bunker Back Entity

This entity represents a teleportation point, specifically designed to return the player to a designated "back" location within a bunker. It features visual effects, particle emissions, and audio cues to indicate its functionality.

## Key Components

### UIInfoComponent
This component defines the in-game name for the entity.

*   **name**: `$teleport_world` - The internal identifier for the teleportation point.

### TeleportComponent
This is the core component responsible for the teleportation functionality.

*   **target\_x\_is\_absolute\_position**: `1` - Indicates that the `target.x` value is an absolute coordinate.
*   **target\_y\_is\_absolute\_position**: `1` - Indicates that the `target.y` value is an absolute coordinate.
*   **target.x**: `-12557` - The absolute X-coordinate to teleport to.
*   **target.y**: `190` - The absolute Y-coordinate to teleport to.

### HitboxComponent
Defines the physical boundaries of the entity.

*   **aabb\_min\_x**: `-15` - Minimum X-axis boundary.
*   **aabb\_min\_y**: `-15` - Minimum Y-axis boundary.
*   **aabb\_max\_x**: `15` - Maximum X-axis boundary.
*   **aabb\_max\_y**: `15` - Maximum Y-axis boundary.

### LightComponent (x2)
These components add visual lighting effects to the entity.

*   **\_enabled**: `1` - Enables the light component.
*   **radius**: `255` (first component), `64` (second component) - The radius of the light's influence.
*   **fade\_out\_time**: `1.5` - Duration for the light to fade out.
*   **r, g, b**: `64, 255, 100` - RGB color values for the light (a greenish hue).
*   **offset\_y**: `-16` - Vertical offset for the light's position.

### SpriteParticleEmitterComponent
Manages the emission of sprite-based particles, creating a visual swirl effect.

*   **sprite\_file**: `data/particles/greenwhirl_0$[1-8].png` - Specifies the sprite sheet for the particles.
*   **lifetime**: `1.5` - Duration each particle exists.
*   **color.a**: `0.75` - Initial alpha transparency of the particles.
*   **color\_change.a**: `-0.8` - How the alpha transparency changes over the particle's lifetime (fades out).
*   **angular\_velocity**: `7.5` - Speed at which particles rotate.
*   **scale\_velocity**: `1.0075` - How the scale of particles changes over their lifetime.
*   **emission\_interval\_min\_frames, emission\_interval\_max\_frames**: `2, 4` - Controls the timing between particle emissions.
*   **count\_min, count\_max**: `1, 1` - Number of particles emitted per emission event.
*   **randomize\_position, randomize\_velocity, randomize\_lifetime, randomize\_angular\_velocity, randomize\_rotation**: Various settings to introduce variation in particle behavior.

### ParticleEmitterComponent (x2)
These components emit material-based particles, contributing to the overall visual effect.

**First Component (General Emission):**

*   **emitted\_material\_name**: `spark_green` - The material of the particles being emitted.
*   **lifetime\_min, lifetime\_max**: `3, 4` - Duration particles exist.
*   **count\_min, count\_max**: `75, 115` - Number of particles emitted per emission interval.
*   **area\_circle\_radius.min, area\_circle\_radius.max**: `15, 15` - The radius of the area from which particles are emitted.
*   **airflow\_force, airflow\_time, airflow\_scale**: `0.051, 1.01, 0.03` - Parameters influencing airflow effects on particles.
*   **emission\_interval\_min\_frames, emission\_interval\_max\_frames**: `12, 12` - Controls the timing between particle emissions.
*   **velocity\_always\_away\_from\_center**: `11` - Particles are pushed away from the center of the emission area.

**Second Component (Focused Emission):**

*   **emitted\_material\_name**: `spark_green` - The material of the particles being emitted.
*   **lifetime\_min, lifetime\_max**: `3, 4` - Duration particles exist.
*   **count\_min, count\_max**: `1, 1` - Number of particles emitted per emission interval.
*   **area\_circle\_radius.min, area\_circle\_radius.max**: `0, 15` - The radius of the area from which particles are emitted.
*   **emission\_interval\_min\_frames, emission\_interval\_max\_frames**: `12, 12` - Controls the timing between particle emissions.
*   **velocity\_always\_away\_from\_center**: `0` - Particles do not have a forced direction away from the center.

### AudioLoopComponent (x2)
These components play looping audio effects associated with the teleportation.

*   **file**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound events.
*   **event\_name**: `misc/teleport_loop` (first component), `misc/teleport_emitter_loop` (second component) - The specific sound events to play.
*   **auto\_play**: `1` - Ensures the audio starts playing automatically when the entity is active.