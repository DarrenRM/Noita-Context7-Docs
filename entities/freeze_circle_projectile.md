---
title: Freeze Circle Projectile
category: entities
---

# Freeze Circle Projectile

This document details the `freeze_circle.xml` entity, which defines a projectile that creates a freezing effect in an area.

## Core Components

### GameAreaEffectComponent

This component defines the area of effect for the projectile.

*   **radius**: The radius of the area affected by the projectile (38 units).
*   **frame_length**: The duration of the effect in frames (90 frames).

### ParticleEmitterComponent (x2)

These components are responsible for emitting cosmetic particles around the projectile.

*   **emitted_material_name**: The material of the particles emitted ("spark\_white").
*   **gravity.y**: The gravitational pull on the particles in the Y-axis (0.0).
*   **lifetime\_min/max**: The minimum and maximum lifetime of the particles in seconds (0.5 to 1.5 seconds).
*   **count\_min/max**: The minimum and maximum number of particles emitted per emission (2-4 for the first, 4 for the second).
*   **render\_on\_grid**: Whether particles are rendered on the game grid (1 for yes).
*   **fade\_based\_on\_lifetime**: Whether particles fade out as their lifetime ends (1 for yes).
*   **area\_circle\_radius.max**: The maximum radius for particle emission (36 units).
*   **cosmetic\_force\_create**: Whether particles are forced to be created (0 for no).
*   **airflow\_force/time/scale**: Parameters controlling airflow effects on particles.
*   **emission\_interval\_min/max\_frames**: The interval between particle emissions in frames (1 frame).
*   **emit\_cosmetic\_particles**: Whether to emit cosmetic particles (1 for yes).
*   **is\_emitting**: Whether the emitter is active (1 for yes).

### Base Component

This entity inherits base properties from `data/entities/projectiles/deck/base_field.xml`.

#### LifetimeComponent

*   **lifetime**: The total lifetime of the projectile in seconds (30 seconds).

#### SpriteComponent

*   **image\_file**: The image file for the projectile's sprite (empty, likely uses a default or is handled by other components).

#### SpriteParticleEmitterComponent (x2)

These components emit snowflake particles.

*   **sprite\_file**: The sprite file for the particles ("data/particles/snowflake\_$[1-2].xml").
*   **lifetime**: The lifetime of the emitted snowflake particles (10 seconds for the first, 3 seconds for the second).
*   **color.r/g/b/a**: The initial color of the particles (white: 1, 1, 1, 1).
*   **color\_change.r/g/b/a**: How the color changes over the particle's lifetime (alpha decreases by 0.5 or 2).
*   **gravity.x/y**: Gravitational pull on the particles (0, 10 for the first, 0, 0 for the second).
*   **velocity\_slowdown**: How much the particle velocity is reduced (0.5 for the first, 0 for the second).
*   **count\_min/max**: Minimum and maximum number of particles emitted (1-2 for the first, 5-10 for the second).
*   **randomize\_rotation.min/max**: Randomization range for particle rotation (-3.1415 to 3.1415 radians).
*   **randomize\_angular\_velocity.min/max**: Randomization range for angular velocity (-15 to 15 degrees/sec).
*   **randomize\_velocity.min/max\_x/y**: Randomization range for particle velocity (-90 to 90 degrees).
*   **randomize\_position.min/max\_x/y**: Randomization range for particle spawn position (-10 to 10 units).
*   **velocity\_always\_away\_from\_center**: Whether particles are always emitted away from the center (1 for yes, only for the second emitter).

#### ProjectileComponent

This component defines the projectile's behavior.

*   **damage\_game\_effect\_entities**: Specifies entities that apply damage or effects when hit ("data/entities/misc/effect\_frozen.xml").
*   **friendly\_fire**: Whether the projectile can damage friendly entities (0 for no).

### MagicConvertMaterialComponent (x5)

These components are responsible for converting surrounding materials into "ice\_static".

*   **kill\_when\_finished**: Whether the component is removed after its effect is complete (0 for no).
*   **from\_material**: The material to be converted (e.g., "water", "water\_ice", "water\_salt", "water\_fading", "water\_static").
*   **steps\_per\_frame**: The number of conversion steps performed per frame (5).
*   **to\_material**: The material to convert to ("ice\_static").
*   **is\_circle**: Whether the conversion happens in a circular area (1 for yes).
*   **radius**: The radius of the conversion area (72 units).

### AudioComponent

This component handles the sound effects for the projectile.

*   **file**: The audio bank file ("data/audio/Desktop/projectiles.bank").
*   **event\_root**: The root event name for projectile sounds ("projectiles/freeze\_circle").

### VariableStorageComponent

*   **name**: The name of the variable ("projectile\_file").
*   **value\_string**: The string value of the variable ("data/entities/projectiles/freeze\_circle.xml").