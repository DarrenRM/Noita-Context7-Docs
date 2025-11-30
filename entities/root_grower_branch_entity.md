---
title: Root Grower Branch Entity
category: entities
---

# Root Grower Branch Entity

This entity represents a branch that grows from a root grower. It inherits its base properties from `root_grower.xml` and adds specific behaviors for its growth and visual effects.

## Key Components

### ParticleEmitterComponent

This component controls the visual particles emitted by the branch.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `_enabled`          | Whether the particle emitter is active (1/0).   |
| `x_pos_offset_min`  | Minimum horizontal offset for particle spawn.   |
| `x_pos_offset_max`  | Maximum horizontal offset for particle spawn.   |
| `y_pos_offset_min`  | Minimum vertical offset for particle spawn.     |
| `y_pos_offset_max`  | Maximum vertical offset for particle spawn.     |
| `count_min`         | Minimum number of particles emitted per burst.  |
| `count_max`         | Maximum number of particles emitted per burst.  |
| `lifetime_min`      | Minimum lifetime of emitted particles.          |
| `lifetime_max`      | Maximum lifetime of emitted particles.          |

### LuaComponent (Spread Logic)

This component executes a Lua script responsible for the spreading behavior of the root grower branch.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `_enabled`            | Whether the Lua component is active (1/0).                               |
| `script_source_file`  | Path to the Lua script file (`data/scripts/props/root_grower_spread.lua`). |
| `execute_every_n_frame` | How often the script is executed (e.g., every 2 frames).                 |

### LuaComponent (Split Logic - Disabled)

This component is present but disabled (`_enabled="0"`), indicating that this branch type does not split.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `_enabled`            | Whether the Lua component is active (1/0).                               |
| `script_source_file`  | Path to the Lua script file (`data/scripts/props/root_grower_split.lua`). |
| `execute_every_n_frame` | Execution frequency (-1 indicates not executed when disabled).           |

### LifetimeComponent

This component defines how long the root grower branch entity will exist before despawning.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_enabled`| Whether the lifetime component is active.   |
| `lifetime`| The duration in seconds before despawning.|

## Inheritance

This entity inherits its fundamental properties and behaviors from the base entity defined in `data/entities/props/root_grower.xml`. This means it likely shares visual assets, collision properties, and other core functionalities with the main root grower.