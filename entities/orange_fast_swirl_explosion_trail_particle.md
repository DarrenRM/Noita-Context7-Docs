---
title: Orange Fast Swirl Explosion Trail Particle
category: entities
---

# Orange Fast Swirl Explosion Trail Particle

This document describes the configuration for a specific particle effect used in Noita, designed to create a fast-moving, orange, swirling trail during explosions.

## Core Components

This particle entity is primarily defined by its movement, emission, and lifetime characteristics.

### VelocityComponent

Controls the basic physics of the particle.

*   **gravity\_y**: `0` - The particle is not affected by gravity.
*   **air\_friction**: `2` - Applies a moderate amount of air friction.
*   **updates\_velocity**: `1` - Enables velocity updates based on physics.

### SimplePhysicsComponent

A placeholder component, indicating the particle interacts with simple physics.

### SetStartVelocityComponent

Determines the initial speed and direction of the emitted particles.

*   **randomize\_speed.min**: `450` - Minimum initial speed.
*   **randomize\_speed.max**: `600` - Maximum initial speed.
*   **randomize\_angle.min**: `0` - Minimum initial angle (in radians).
*   **randomize\_angle.max**: `6.283185` (approximately 2π) - Maximum initial angle, allowing for a full circle.

### ParticleEmitterComponent

This is the main component responsible for generating and managing the particle trail.

*   **emitted\_material\_name**: `"spark"` - The material/visual appearance of the particles.
*   **delay\_frames**: `2` - A short delay before emission starts.
*   **gravity.y**: `0` - Particles are not affected by gravity during emission.
*   **count\_min**: `0` - Minimum number of particles to emit per interval.
*   **count\_max**: `1` - Maximum number of particles to emit per interval.
*   **lifetime\_min**: `0.5` - Minimum lifetime of individual particles.
*   **lifetime\_max**: `2.5` - Maximum lifetime of individual particles.
*   **emit\_real\_particles**: `0` - Indicates these are not "real" world particles but visual effects.
*   **render\_on\_grid**: `0` - Particles are not rendered on the game grid.
*   **is\_trail**: `1` - Crucially, this enables the particle to function as a trail.
*   **trail\_gap**: `1` - The spacing between particles in the trail.
*   **airflow\_force**: `0.3` - A force applied to the particles, likely for swirling effects.
*   **airflow\_time**: `0.01` - The duration for which airflow is applied.
*   **airflow\_scale**: `0.22` - The intensity or scale of the airflow effect.
*   **emit\_cosmetic\_particles**: `1` - These are cosmetic particles, not gameplay-affecting ones.
*   **emission\_interval\_min\_frames**: `1` - Minimum frames between emissions.
*   **emission\_interval\_max\_frames**: `1` - Maximum frames between emissions, meaning continuous emission.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **is\_emitting**: `1` - The emitter is active.

### LifetimeComponent

Determines the overall lifespan of the entity that spawns these particles.

*   **lifetime**: `100` - Base lifespan in seconds.
*   **randomize\_lifetime.min**: `-75` - Minimum reduction in lifespan.
*   **randomize\_lifetime.max**: `75` - Maximum increase in lifespan.

### LuaComponent

Attaches custom Lua scripting to the particle entity.

*   **script\_source\_file**: `"data/scripts/particles/swirl_movement.lua"` - Specifies the Lua script responsible for custom particle behavior, likely handling the swirling motion.
*   **execute\_every\_n\_frame**: `1` - The script runs every frame.