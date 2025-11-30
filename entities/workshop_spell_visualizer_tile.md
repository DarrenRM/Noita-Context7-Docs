---
title: Workshop Spell Visualizer Tile
category: entities
---

# Workshop Spell Visualizer Tile

This entity represents a visual element used in the workshop for spell visualization. It's a simple tile with a sprite and a lifetime component.

## Key Components

### SpriteComponent

This component defines the visual appearance of the tile.

| Attribute   | Value                               | Description                                                              |
| :---------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `image_file`| `data/ui_gfx/gun_actions/empty.png` | The image file used for the sprite. In this case, it's an empty image. |
| `offset_x`  | `2`                                 | Horizontal offset of the sprite.                                         |
| `offset_y`  | `2`                                 | Vertical offset of the sprite.                                           |
| `z_index`   | `1`                                 | Determines the drawing order of the sprite.                              |

### LifetimeComponent

This component controls how long the entity exists and if it fades out.

| Attribute      | Value | Description                                      |
| :------------- | :---- | :----------------------------------------------- |
| `lifetime`     | `160` | The duration in frames before the entity is removed. |
| `fade_sprites` | `1`   | Whether the sprites should fade out over their lifetime. |