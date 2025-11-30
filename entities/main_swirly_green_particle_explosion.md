---
title: Main Swirly Green Particle Explosion
category: entities
---

# Main Swirly Green Particle Explosion

This entity defines a specific type of particle explosion, characterized by swirly green visual effects. It primarily functions by loading other pre-defined entity files that represent different components of the explosion.

## Key Components

The explosion is constructed from several `LoadEntitiesComponent` instances, each responsible for spawning a particular visual or functional element.

### Loaded Entities

| Entity File                                                    | Description                                                              | Count Min | Count Max | Kill Entity | Timeout Frames |
| :------------------------------------------------------------- | :----------------------------------------------------------------------- | :-------- | :-------- | :---------- | :------------- |
| `data/entities/particles/particle_explosion/explosion_flare.xml` | Spawns a basic explosion flare.                                          | 1         | 1         | 0           | -              |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | Creates a hole in the fog of war, likely for visual clarity.             | 1         | 1         | 0           | -              |
| `data/entities/particles/particle_explosion/explosion_trail_swirl_green.xml` | Generates the characteristic swirly green trails of the explosion.       | 12        | 24        | 0           | -              |
| `data/entities/particles/particle_explosion/explosion_smoke_pillar_green.xml` | Creates a green smoke pillar as part of the explosion.                   | 1         | 1         | 1           | 3              |

## Key Attributes

*   **`entity_file`**: Specifies the path to another entity file to be loaded and instantiated. This is the core mechanism for building complex effects from simpler components.
*   **`count.min` / `count.max`**: Determines the minimum and maximum number of instances of the loaded entity to spawn. This allows for variation in the intensity or appearance of the effect.
*   **`kill_entity`**: A flag (0 or 1) indicating whether the entity that loaded this component should be destroyed after the component's action is complete.
*   **`timeout_frames`**: Specifies a delay in frames before the `kill_entity` action is performed. This is useful for effects that have a duration.