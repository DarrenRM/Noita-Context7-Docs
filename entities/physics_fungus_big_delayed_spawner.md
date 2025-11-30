---
title: Physics Fungus Big Delayed Spawner
category: entities
---

# Physics Fungus Big Delayed Spawner

This entity is a spawner that creates a `physics_fungus_big` entity after a delay.

## Key Components

### LoadEntitiesComponent

This component handles the spawning of other entities.

| Attribute      | Description                                                              |
|----------------|--------------------------------------------------------------------------|
| `entity_file`  | The path to the entity file to be spawned.                               |
| `kill_entity`  | If set to "1", the spawner entity will be destroyed after spawning.      |
| `count.min`    | The minimum number of entities to spawn.                                 |
| `count.max`    | The maximum number of entities to spawn.                                 |
| `timeout_frames` | The delay in frames before the entity is spawned.                        |