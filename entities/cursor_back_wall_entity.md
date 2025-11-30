---
title: Cursor Back Wall Entity
category: entities
---

# Cursor Back Wall Entity

This entity defines a visual element that appears behind the player's cursor, likely for aesthetic or informational purposes. It consists of two sprite components.

## Sprite Components

### Sprite 1 (Back Wall)

This component defines the background visual.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`| `data/temp/building/back_wall16.xml`| Specifies the image file for the back wall sprite.                          |
| `alpha`     | `0.5`                               | Sets the transparency of the sprite (50% opaque).                           |
| `z_index`   | `2`                                 | Determines the drawing order; lower values are drawn behind higher values. |

### Sprite 2 (Cursor)

This component defines the visual that follows the cursor.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`| `data/temp/building/cursor_16x16.png`| Specifies the image file for the cursor sprite.                             |
| `offset_x`  | `8`                                 | Offsets the sprite horizontally by 8 pixels.                                |
| `offset_y`  | `8`                                 | Offsets the sprite vertically by 8 pixels.                                  |
| `emissive`  | `1`                                 | Makes the sprite emit light, potentially affecting its appearance.          |
| `alpha`     | `0.8`                               | Sets the transparency of the sprite (80% opaque).                           |
| `z_index`   | `10`                                | Determines the drawing order; this sprite is drawn on top of the back wall. |