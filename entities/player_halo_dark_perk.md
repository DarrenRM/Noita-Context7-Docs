---
title: Player Halo (Dark) Perk
category: entities
---

# Player Halo (Dark) Perk

This entity defines a dark variant of the player's halo perk in Noita. It inherits its base functionality from `player_halo_light.xml` and modifies its visual and light properties.

## Key Attributes

### SpriteComponent
This component defines the visual appearance of the halo.

| Attribute     | Value                               | Description                               |
|---------------|-------------------------------------|-------------------------------------------|
| `image_file`  | `data/enemies_gfx/player_halo_dark.png` | Specifies the texture file for the halo. |

### LightComponent
This component controls the light emitted by the halo.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `r`       | 128   | Red component of the light color.         |
| `g`       | 5     | Green component of the light color.       |
| `b`       | 5     | Blue component of the light color.        |

### ParticleEmitterComponent
This component controls the particles emitted by the halo.

| Attribute             | Value          | Description                                     |
|-----------------------|----------------|-------------------------------------------------|
| `emitted_material_name` | `spark_red`    | The material name of the particles to be emitted. |