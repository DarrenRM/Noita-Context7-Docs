---
title: Main Swirly Red Giga Particle Explosion
category: entities
---

# Main Swirly Red Giga Particle Explosion

This entity defines a complex particle explosion effect, primarily composed of various pre-defined explosion particle entities. It's designed to create a visually striking, large-scale red explosion with swirling trails and smoke.

## Key Components

The explosion is constructed by loading several other entity files, each contributing specific visual elements.

### LoadEntitiesComponent Breakdown

This component is used to spawn other entities. The key attributes are:

*   `entity_file`: The path to the entity file to be loaded.
*   `count.min`: The minimum number of entities to spawn.
*   `count.max`: The maximum number of entities to spawn.
*   `kill_entity`: If set to `1`, the entity that loaded this component will be destroyed after the spawned entities are created.
*   `timeout_frames`: The number of frames to wait before spawning (used with `kill_entity="1"`).

#### Loaded Entities:

| `entity_file`                                                      | `count.min` | `count.max` | `kill_entity` | `timeout_frames` | Description                                                                 |
| :----------------------------------------------------------------- | :---------- | :---------- | :------------ | :--------------- | :-------------------------------------------------------------------------- |
| `data/entities/particles/particle_explosion/explosion_flare.xml`   | 1           | 1           | 0             | -                | Spawns a basic explosion flare.                                             |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | 1           | 1           | 0             | -                | Spawns a flare that also creates a hole in the fog of war.                  |
| `data/entities/particles/particle_explosion/explosion_trail_swirl_red_fast.xml` | 15          | 20          | 0             | -                | Spawns multiple fast, red swirling trails.                                  |
| `data/entities/particles/particle_explosion/explosion_trail_spark_red_large.xml` | 14          | 16          | 0             | -                | Spawns numerous large, red sparks.                                          |
| `data/entities/particles/particle_explosion/explosion_smoke_pillar_red.xml` | 1           | 1           | 1             | 3                | Spawns a red smoke pillar and then destroys the parent entity after 3 frames. |

## Summary

This entity acts as a master controller for a complex explosion effect. By strategically loading other pre-defined particle entities with varying counts and timings, it orchestrates a dynamic and visually rich explosion. The inclusion of `explosion_smoke_pillar_red.xml` with `kill_entity="1"` suggests that this specific particle effect is intended to be a temporary, self-contained explosion that doesn't persist as a game entity itself, but rather as a visual event.