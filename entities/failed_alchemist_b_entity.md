---
title: Failed Alchemist B Entity
category: entities
---

# Failed Alchemist B Entity

This document details the configuration for the "Failed Alchemist B" entity in Noita, focusing on its AI, combat, and visual properties.

## Core Attributes

The Failed Alchemist B is a flying creature with a focus on detection and a unique death effect.

### Base Entity Configuration

The entity inherits from `base_enemy_basic.xml`, providing fundamental enemy behaviors.

*   **ItemChestComponent**: Disabled (`_enabled="0"`). This entity does not drop items from a chest.
*   **LuaComponent**: Disabled (`_enabled="0"`). No specific Lua script is attached to the base component.

### AnimalAIComponent

This component governs the creature's artificial intelligence and sensory capabilities.

*   **preferred\_job**: `JobDefault` - Indicates a standard AI behavior.
*   **attack\_melee\_enabled**: `0` - Cannot perform melee attacks.
*   **creature\_detection\_range\_x/y**: `400` - Detects creatures within a 400-unit radius.
*   **food\_material**: `blood` - Consumes blood as sustenance.
*   **needs\_food**: `0` - Does not require food to survive.
*   **sense\_creatures**: `1` - Actively senses other creatures.
*   **attack\_ranged\_enabled**: `0` - Cannot perform ranged attacks.
*   **can\_fly**: `1` - Capable of flight.

### DamageModelComponent

Defines the entity's health, damage resistances, and how it reacts to being damaged.

*   **hp**: `3` - Has a low health pool.
*   **blood\_material**: `slime` - When damaged, it bleeds slime.
*   **blood\_spray\_material**: `slime` - Blood spray also consists of slime.
*   **blood\_sprite\_directional**: `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` - Uses purple directional blood splatters.
*   **blood\_sprite\_large**: `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` - Uses purple large blood splatters.
*   **ragdoll\_material**: `rock_static_glow` - Its ragdoll is made of glowing static rock.
*   **fire\_probability\_of\_ignition**: `0.01` - Low chance of igniting from fire.
*   **damage\_multipliers**:
    *   `projectile`: `0.6` - Takes 60% damage from projectiles.
    *   `holy`: `1.2` - Takes 120% damage from holy sources.

### SpriteComponent

Determines the visual appearance of the entity.

*   **image\_file**: `data/enemies_gfx/failed_alchemist_b.xml` - Uses a custom sprite definition.

### PathFindingComponent

Defines how the entity navigates the environment.

*   **can\_fly**: `1` - Can fly.
*   **can\_jump**: `0` - Cannot jump.
*   **can\_walk**: `0` - Cannot walk.

### GenomeDataComponent

Provides genetic information for creature interactions and AI.

*   **herd\_id**: `mage` - Belongs to the "mage" herd.
*   **food\_chain\_rank**: `6` - High rank in the food chain.
*   **is\_predator**: `1` - Acts as a predator.

### CharacterPlatformingComponent

Handles movement and platforming mechanics.

*   **run\_velocity**: `1` - Standard running speed.
*   **jump\_velocity\_y**: `-12` - Vertical jump force.

### CameraBoundComponent

Controls how the entity interacts with the camera's view.

*   **max\_count**: `30` - Limits the number of these entities that can be active within camera bounds.
*   **distance**: `160000` - The maximum distance from the camera where the entity can exist.

### HitboxComponent

Defines the collision area for interactions.

*   **aabb\_max\_x**: `3`
*   **aabb\_max\_y**: `2`
*   **aabb\_min\_x**: `-3`
*   **aabb\_min\_y**: `-20`

### CharacterDataComponent

General character data, including collision and mass.

*   **collision\_aabb\_min\_x/max\_x/min\_y/max\_y**: Defines the precise collision box.
*   **mass**: `1.8` - Has a moderate mass.

## Attached Components

These components add specific functionalities to the entity.

### AudioLoopComponent

Plays a looping sound effect.

*   **file**: `data/audio/Desktop/animals.bank`
*   **event\_name**: `animals/failed_alchemist_b/magic_loop`
*   **auto\_play**: `1` - Starts playing automatically.

### AudioComponent

Manages general sound events for the entity.

*   **file**: `data/audio/Desktop/animals.bank`
*   **event\_root**: `animals/failed_alchemist_b`

### Entity (for attached effects)

This nested entity contains components for visual effects and area damage.

#### InheritTransformComponent

Applies a positional offset to the attached components.

*   **Transform**: `position.y="-8"` - Shifts the attached effects down by 8 units.

#### AreaDamageComponent

Deals damage to entities within a specific area.

*   **aabb\_min/max**: Defines a 128x128 unit area around the entity.
*   **damage\_per\_frame**: `0.09` - Deals minor damage over time.
*   **update\_every\_n\_frame**: `40` - Updates damage calculation every 40 frames.
*   **entities\_with\_tag**: `prey` - Only affects entities tagged as "prey".
*   **damage\_type**: `DAMAGE_PROJECTILE` - Damage is classified as projectile.
*   **death\_cause**: `$animal_failed_alchemist_b` - The entity that caused the damage upon death.

#### SpriteParticleEmitterComponent

Emits glowing particles.

*   **sprite\_file**: `data/particles/failed_alchemist_glow_0$[1-6].png` - Uses a sequence of glow sprites.
*   **lifetime**: `1` - Particles last for 1 frame.
*   **color**: White (`1, 1, 1, 1`).
*   **color\_change**: Alpha decreases over time (`-2`).
*   **gravity**: `0.1` - Slight downward gravity.
*   **emissive**: `1` - Particles emit light.
*   **additive**: `1` - Particles are additive.
*   **emission\_interval\_min/max\_frames**: `5-10` - Emits particles periodically.
*   **count\_min/max**: `1` - Emits one particle at a time.
*   **randomize\_position**: Varies particle spawn location within a radius.
*   **randomize\_velocity**: Varies particle initial velocity.

#### ParticleEmitterComponent (x2)

These components emit "spark\_purple\_bright" particles for visual flair.

*   **emitted\_material\_name**: `spark_purple_bright`
*   **gravity**: `0.0` - No gravity applied.
*   **lifetime\_min/max**: Varies particle lifespan.
*   **count\_min/max**: Varies the number of particles emitted.
*   **render\_on\_grid**: `1` - Particles are rendered on the game grid.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade as their lifetime ends.
*   **area\_circle\_radius**: Defines the emission area.
*   **cosmetic\_force\_create**: `0` - Not purely cosmetic.
*   **airflow\_force/time/scale**: Affects particle movement with airflow.
*   **emission\_interval\_min/max\_frames**: Controls emission frequency.
*   **emit\_cosmetic\_particles**: `1` - Emits cosmetic particles.
*   **x\_vel\_min/max**, **y\_vel\_min/max**: Defines initial particle velocity ranges.
*   **is\_emitting**: `1` - The emitter is active.

### LuaComponent (for death script)

Attaches a specific Lua script to handle the entity's death.

*   **script\_death**: `data/scripts/animals/failed_alchemist_b_death.lua` - Executes this script upon the entity's death.