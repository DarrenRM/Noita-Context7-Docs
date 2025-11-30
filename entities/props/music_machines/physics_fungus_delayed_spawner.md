---
title: Physics Fungus Delayed Spawner
category: entities/props/music_machines
---

# Physics Fungus Delayed Spawner

This entity is a simple spawner that creates a `physics_fungus.xml` entity after a short delay. It's likely used in music machines or other timed events where a physics-based fungus needs to appear.

## Key Components

### LoadEntitiesComponent

This component handles the spawning of other entities.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `entity_file`  | The path to the entity file to be spawned. In this case, `data/entities/props/physics_fungus.xml`. |
| `kill_entity`  | If set to `1`, the spawner entity will be destroyed after spawning.         |
| `count.min`    | The minimum number of entities to spawn.                                    |
| `count.max`    | The maximum number of entities to spawn.                                    |
| `timeout_frames` | The number of frames to wait before spawning the entity. This controls the delay. |