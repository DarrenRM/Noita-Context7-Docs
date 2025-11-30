---
title: Boss Centipede Shield Entity
category: entities
---

# Boss Centipede Shield Entity

This document describes the `boss_centipede_shield_strong.xml` entity, which defines the visual and functional components of the boss centipede's energy shield.

## Core Components

The shield entity is primarily composed of visual elements, a Lua script for its behavior, and audio cues.

### SpriteComponent

This component defines the visual appearance of the shield.

| Attribute          | Description                                                              |
| :----------------- | :----------------------------------------------------------------------- |
| `image_file`       | Path to the sprite image (`data/entities/animals/boss_centipede/boss_centipede_shield.png`). |
| `alpha`            | Transparency of the sprite (1 for fully opaque).                         |
| `emissive`         | Whether the sprite emits light (1 for emissive).                         |
| `offset_x`, `offset_y` | Offset of the sprite from the entity's origin (50, 50).                  |
| `update_transform_rotation` | Whether the sprite's rotation updates with the entity's transform (0 for no). |

### LightComponent

This component adds a light source to the shield.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `radius`  | The radius of the light (150).                  |
| `r`, `g`, `b` | The RGB color values of the light (255, 35, 255 - a vibrant pink). |

### LuaComponent

This component enables the shield's behavior through a Lua script.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script (`data/entities/animals/boss_centipede/boss_centipede_shield.lua`). |
| `execute_every_n_frame` | How often the script is executed (1 frame).                              |

### ParticleEmitterComponent (x2)

These components are responsible for emitting visual particle effects around the shield.

**First Emitter (Attracted Particles):**

| Attribute               | Description