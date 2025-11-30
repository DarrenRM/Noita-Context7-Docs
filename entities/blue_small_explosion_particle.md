---
title: Blue Small Explosion Particle
category: entities
---

# Blue Small Explosion Particle

This entity defines a small blue explosion effect, composed of several other particle entities.

## Key Components

### LoadEntitiesComponent

This component is used to load other entities, effectively creating the visual effect of the explosion.

| Attribute      | Description                                                              |
|----------------|--------------------------------------------------------------------------|
| `count.min`    | Minimum number of entities to load.                                      |
| `count.max`    | Maximum number of entities to load.                                      |
| `kill_entity`  | Whether to kill the parent entity after loading. `0` means no, `1` means yes. |
| `entity_file`  | The path to the entity file to load.                                     |

#### Loaded Entities:

| `entity_file`                                                              | `count.min` | `count.max` | `kill_entity` | Description                                                              |
|----------------------------------------------------------------------------|-------------|-------------|---------------|--------------------------------------------------------------------------|
| `data/entities/particles/particle_explosion/explosion_flare_blue.xml`      | 1           | 1           | 0             | Loads a blue flare particle.                                             |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | 1           | 1           | 0             | Loads a particle that creates a hole in the fog of war.                  |
| `data/entities/particles/particle_explosion/explosion_trail_spark_blue_small.xml` | 6           | 9           | 1             | Loads multiple small blue spark trail particles, and kills the parent. |