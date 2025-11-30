---
title: Blue Explosion Particle Entity
category: entities
---

# Blue Explosion Particle Entity

This entity defines a blue explosion effect, composed of several sub-particle entities.

## Key Components

### LoadEntitiesComponent

This component is used to spawn other entities when this entity is activated.

| Attribute     | Description                                                              |
|---------------|--------------------------------------------------------------------------|
| `count.min`   | Minimum number of entities to spawn.                                     |
| `count.max`   | Maximum number of entities to spawn.                                     |
| `kill_entity` | Whether to destroy the parent entity after spawning. `1` means destroy. |
| `entity_file` | The path to the entity file to load.                                     |

#### Loaded Entities:

| Entity File                                                              | Count Min | Count Max | Kill Entity |
|--------------------------------------------------------------------------|-----------|-----------|-------------|
| `data/entities/particles/particle_explosion/explosion_flare_blue.xml`    | 1         | 1         | 0           |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | 1         | 1         | 0           |
| `data/entities/particles/particle_explosion/explosion_trail_spark_blue.xml` | 10        | 12        | 1           |