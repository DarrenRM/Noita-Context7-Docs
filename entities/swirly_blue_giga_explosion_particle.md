---
title: Swirly Blue Giga Explosion Particle
category: entities
---

# Swirly Blue Giga Explosion Particle

This entity defines a complex explosion effect, primarily composed of various particle entities. It's designed to create a visually striking "swirly blue giga" explosion.

## Key Components

The explosion is constructed by loading several other particle entities using the `LoadEntitiesComponent`. Each `LoadEntitiesComponent` specifies how many instances of a particular particle effect to spawn and whether to kill the parent entity after spawning.

### Loaded Entities

| Entity File                                                              | Count Min | Count Max | Kill Entity | Timeout Frames | Description                                                              |
| :----------------------------------------------------------------------- | :-------- | :-------- | :---------- | :------------- | :----------------------------------------------------------------------- |
| `data/entities/particles/particle_explosion/explosion_flare.xml`         | 1         | 1         | 0           | -              | Spawns a basic explosion flare.                                          |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | 1         | 1         | 0           | -              | Creates a hole in the fog of war, likely for visual effect.              |
| `data/entities/particles/particle_explosion/explosion_trail_swirl_blue_fast.xml` | 15        | 20        | 0           | -              | Generates numerous fast-moving blue swirling trails.                     |
| `data/entities/particles/particle_explosion/explosion_trail_spark_blue_large.xml` | 14        | 16        | 0           | -              | Spawns a significant number of large blue sparks.                        |
| `data/entities/particles/particle_explosion/explosion_smoke_pillar_grey.xml` | 1         | 1         | 1           | 3              | Creates a grey smoke pillar and kills the parent entity after 3 frames. |

## Core Functionality

The primary function of this entity is to act as a container and spawner for a collection of pre-defined particle effects. It orchestrates the appearance of a large, visually dynamic explosion by layering different particle types. The `kill_entity="1"` on the smoke pillar ensures the explosion effect is temporary and cleans itself up.