---
title: Teleport Bunker Entity
category: entities
---

# Teleport Bunker Entity

This entity represents a teleportation point within the game world. It's a static object that, when interacted with, transports the player to a predefined location.

## Key Components

### UIInfoComponent
This component defines the in-game name displayed for the entity.

*   **name**: `$teleport_world` - The internal identifier for the teleport world.

### TeleportComponent
This is the core component responsible for the teleportation functionality.

*   **target\_x\_is\_absolute\_position**: `1` - Indicates that `target.x` is an absolute world coordinate.
*   **target\_y\_is\_absolute\_position**: `1` - Indicates that `target.y` is an absolute world coordinate.
*   **target.x**: `-12400` - The absolute X-coordinate to teleport to.
*   **target.y**: `391` - The absolute Y-coordinate to teleport to.

### HitboxComponent
Defines the physical boundaries of the entity for collision detection.

*   **aabb\_min\_x**: `-15` - Minimum X-axis bounding box coordinate.
*   **aabb\_min\_y**: `-15` - Minimum Y-axis bounding box coordinate.
*   **aabb\_max\_x**: `15` - Maximum X-axis bounding box coordinate.
*   **aabb\_max\_y**: `15` - Maximum Y-axis bounding box coordinate.

### LightComponent (x2)
These components add visual lighting effects to the entity.

*   **\_enabled**: `1` - Enables the light component.
*   **radius**: `255` (first component), `64` (second component) - The radius of the light.
*   **fade\_out\_time**: `1.5` - How long it takes for the light to fade out.
*   **r, g, b**: `64, 255, 100` - The RGB color values of the light (a greenish hue).
*   **offset\_y**: `-16` - Vertical offset for the light's position.

### SpriteParticleEmitterComponent
Manages the emission of sprite-based particles, creating visual effects around the teleport.

*   **sprite\_file**: `data/particles/greenwhirl_0$[1-8].png` - The sprite sheet used for particles.
*   **lifetime**: `1.5` - Duration each particle exists.
*   **color.a**: `0.75` - Initial alpha transparency of particles.
*   **color\_change.a**: `-0.8` - How much the alpha changes over the particle's lifetime (fades out).
*   **angular\_velocity**: `7.5` - Speed of particle rotation.
*   **scale\_velocity**: `1.0075` - How much the particle's scale changes over its lifetime.
*   **emission\_interval\_min\_frames, emission\_interval\_max\_frames**: `2, 4` - Controls the timing of particle emissions.
*   **count\_min, count\_max**: `1, 1` - Number of particles emitted per interval.
*   **randomize\_position, randomize\_velocity, randomize\_lifetime, randomize\_angular\_velocity, randomize\_rotation**: Various settings to add variation to emitted particles.

### ParticleEmitterComponent (x2)
These components emit material-based particles, contributing to the visual and auditory feedback of the teleport.

*   **emitted\_material\_name**: `spark_green` - The material of the particles being emitted.
*   **lifetime\_min, lifetime\_max**: `3, 4` - Duration particles exist.
*   **count\_min, count\_max**: `75, 115` (first component), `1, 1` (second component) - Number of particles emitted.
*   **area\_circle\_radius.min, area\_circle\_radius.max**: `15, 15` (first component), `0, 15` (second component) - The area from which particles are emitted.
*   **cosmetic\_force\_create**: `1` - Ensures particles are created even if not strictly necessary for gameplay.
*   **airflow\_force, airflow\_time, airflow\_scale**: Parameters influencing particle movement due to simulated airflow.
*   **emission\_interval\_min\_frames, emission\_interval\_max\_frames**: `12, 12` - Controls the timing of particle emissions.
*   **emit\_cosmetic\_particles**: `1` - Emits particles that are purely visual.
*   **velocity\_always\_away\_from\_center**: `11` (first component), `0` (second component) - Controls particle direction relative to the emitter's center.

### AudioLoopComponent (x2)
These components play looping sound effects associated with the teleport.

*   **file**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound events.
*   **event\_name**: `misc/teleport_loop` and `misc/teleport_emitter_loop` - The specific sound events to play.
*   **auto\_play**: `1` - Starts the sound automatically when the entity is active.

### LifetimeComponent
Determines how long the entity will exist in the game world.

*   **lifetime**: `600` - The entity will exist for 600 game frames.