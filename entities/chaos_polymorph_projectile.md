---
title: Chaos Polymorph Projectile
category: entities
---

# Chaos Polymorph Projectile

This document details the `chaos_polymorph.xml` entity, which defines a projectile that can cause random polymorph effects.

## Core Components

### GameAreaEffectComponent
This component defines the area of effect for the projectile.

*   **radius**: `24` - The radius of the area affected by the projectile.
*   **frame_length**: `70` - The duration (in frames) for which the area effect persists.

### Base Component
This projectile inherits its base properties from `data/entities/projectiles/deck/base_field.xml`.

*   **LifetimeComponent**:
    *   **lifetime**: `10` - The projectile exists for 10 seconds.

### ProjectileComponent
This component defines the projectile's behavior and effects.

*   **damage_game_effect_entities**: `data/entities/misc/effect_polymorph_random.xml,` - When the projectile hits, it triggers a random polymorph effect defined in this external entity.
*   **friendly_fire**: `1` - The projectile can damage allies.

## Particle Emitters

This projectile utilizes several `ParticleEmitterComponent` and `SpriteParticleEmitterComponent` to create visual effects.

### SpriteParticleEmitterComponent (Shine)
This component is responsible for emitting small, shiny particles.

*   **sprite\_file**: `data/particles/shine_03.xml` - Uses a predefined shine particle.
*   **lifetime**: `4` - Particles last for 4 seconds.
*   **color**: `r="1" g="1" b="1" a="1"` - White color.
*   **color\_change**: `r="0" g="0" b="0" a="-1"` - Alpha decreases over time.
*   **randomize\_rotation**: `min="-3.1415" max="3.1415"` - Random initial rotation.
*   **randomize\_angular\_velocity**: `min="-15" max="15"` - Random angular velocity.
*   **is\_emitting**: `0` - This specific emitter is not actively emitting in this configuration, likely used as a base for other emitters.

### SpriteParticleEmitterComponent (Main Emission)
This component handles the primary visual emission of particles when the projectile is active.

*   **sprite\_file**: `data/particles/shine_03.xml`
*   **lifetime**: `4`
*   **color**: `r="1" g="1" b="1" a="1"`
*   **color\_change**: `r="0" g="0" b="0" a="-1"`
*   **velocity**: `x="0" y="0"` - Initial velocity is zero.
*   **gravity**: `x="0" y="0"` - No gravity applied.
*   **velocity\_slowdown**: `0`
*   **count\_min**: `5`, **count\_max**: `10` - Emits between 5 and 10 particles per emission.
*   **scale**: `x="1" y="1"`
*   **scale\_velocity**: `x="0" y="0"`
*   **emission\_interval\_min\_frames**: `1`, **emission\_interval\_max\_frames**: `1` - Emits every frame.
*   **randomize\_rotation**: `min="-3.1415" max="3.1415"`
*   **randomize\_angular\_velocity**: `min="-15" max="15"`
*   **randomize\_velocity**: `min_x="-50" max_x="50" min_y="-50" max_y="50"` - Particles are emitted with random velocities.
*   **randomize\_position**: `min_x="-10" max_x="10" min_y="-10" max_y="10"` - Particles are emitted with slight positional randomization.
*   **velocity\_always\_away\_from\_center**: `1` - Particles are pushed away from the center of emission.
*   **is\_emitting**: `0` - Similar to the previous shine emitter, this is likely a base configuration.

### ParticleEmitterComponent (Primary Material Emission)
This component emits the main visual material of the projectile.

*   **emitted\_material\_name**: `plasma_fading_pink` - The material used for the emitted particles.
*   **gravity**: `y="0.0"` - No gravity.
*   **lifetime\_min**: `0.5`, **lifetime\_max**: `1.5` - Particles last between 0.5 and 1.5 seconds.
*   **count\_min**: `15`, **count\_max**: `30` - Emits between 15 and 30 particles per emission.
*   **render\_on\_grid**: `1` - Particles are rendered on the game grid.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade out as their lifetime ends.
*   **area\_circle\_radius**: `max="24"` - Particles are emitted within a 24-unit radius.
*   **cosmetic\_force\_create**: `0`
*   **airflow\_force**: `2.5`, **airflow\_time**: `1.9`, **airflow\_scale**: `0.15` - Airflow properties affecting particle movement.
*   **emission\_interval\_min\_frames**: `1`, **emission\_interval\_max\_frames**: `1` - Emits every frame.
*   **emit\_cosmetic\_particles**: `1`
*   **x\_vel\_min**: `-40`, **x\_vel\_max**: `40`
*   **y\_vel\_min**: `-40`, **y\_vel\_max**: `40` - Particles are emitted with a wide range of velocities.
*   **is\_emitting**: `1` - This emitter is actively producing particles.

### ParticleEmitterComponent (Secondary Material Emission)
This component emits a secondary set of particles, likely for lingering effects.

*   **emitted\_material\_name**: `plasma_fading_pink`
*   **gravity**: `y="0.0"`
*   **lifetime\_min**: `5.5`, **lifetime\_max**: `15.5` - Particles have a longer lifetime.
*   **count\_min**: `5`, **count\_max**: `15` - Emits fewer particles.
*   **render\_on\_grid**: `1`
*   **fade\_based\_on\_lifetime**: `1`
*   **area\_circle\_radius**: `max="24"`
*   **cosmetic\_force\_create**: `0`
*   **airflow\_force**: `0.5`, **airflow\_time**: `1.9`, **airflow\_scale**: `0.15` - Lower airflow force.
*   **emission\_interval\_min\_frames**: `1`, **emission\_interval\_max\_frames**: `1`
*   **emit\_cosmetic\_particles**: `1`
*   **x\_vel\_min**: `-20`, **x\_vel\_max**: `20`
*   **y\_vel\_min**: `-20`, **y\_vel\_max**: `20` - Particles have a narrower velocity range.
*   **is\_emitting**: `1` - This emitter is actively producing particles.

## AreaDamageComponent
This component defines a damage-over-time effect within a specific area.

*   **aabb\_min**: `x="-16" y="-16"`
*   **aabb\_max**: `x="16" y="16"` - Defines a 32x32 bounding box for damage.
*   **damage\_per\_frame**: `0.06` - Deals 0.06 damage per frame.
*   **update\_every\_n\_frame**: `1` - Damage is applied every frame.
*   **\_enabled**: `0` - This component is currently disabled.

## VariableStorageComponent
Stores a variable related to the projectile's file path.

*   **name**: `projectile_file`
*   **value\_string**: `data/entities/projectiles/chaos_polymorph.xml` - Stores the path to this entity file.