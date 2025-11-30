---
title: Fungus Sprite Animations
category: entities_gfx
---

# Fungus Sprite Animations

This document details the sprite animations for the "fungus" enemy in Noita, as defined in `fungus.xml`. It focuses on the key attributes of each animation and the events associated with them.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/fungus.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `13` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### `stand` Animation

*   **name**: `stand`
*   **frame\_count**: `12`
*   **frame\_width**: `16`
*   **frame\_height**: `16`
*   **frames\_per\_row**: `12`
*   **frame\_wait**: `0.12` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `1` - Defines the starting Y position of this animation strip on the sprite sheet.

### `walk` Animation

*   **name**: `walk`
*   **frame\_count**: `6`
*   **frame\_width**: `17`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.2` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1` - Indicates the sprite is slightly shrunk for this animation.

#### Events for `walk`:

| Frame | Name  | Probability | Check Physics Material | Max Distance | On Finished |
| :---- | :---- | :---------- | :--------------------- | :----------- | :---------- |
| 2     | step  | 1           | 1                      | 500          | 0           |
| 5     | step  | 1           | 1                      | 500          | 0           |

### `run` Animation

*   **name**: `run`
*   **frame\_count**: `6`
*   **frame\_width**: `17`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.2` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1`

#### Events for `run`:

| Frame | Name  | Probability | Check Physics Material | Max Distance | On Finished |
| :---- | :---- | :---------- | :--------------------- | :----------- | :---------- |
| 2     | step  | 1           | 1                      | 500          | 0           |
| 5     | step  | 1           | 1                      | 500          | 0           |

### `burn` Animation

*   **name**: `burn`
*   **frame\_count**: `6`
*   **frame\_width**: `17`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `6`
*   **frame\_wait**: `0.2` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `18`
*   **shrink\_by\_one\_pixel**: `1`

#### Events for `burn`:

| Frame | Name  | Probability | Check Physics Material | Max Distance | On Finished |
| :---- | :---- | :---------- | :--------------------- | :----------- | :---------- |
| 2     | step  | 1           | 1                      | 500          | 0           |
| 5     | step  | 1           | 1                      | 500          | 0           |

### `jump_up` Animation

*   **name**: `jump_up`
*   **frame\_count**: `1`
*   **frame\_width**: `17`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `1`
*   **frame\_wait**: `0.2` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `35`
*   **shrink\_by\_one\_pixel**: `1`

#### Events for `jump_up`:

| Frame | Name | Probability | Check Physics Material | Max Distance | On Finished |
| :---- | :--- | :---------- | :--------------------- | :----------- | :---------- |
| 0     | jump | 1           | 1                      | 500          | 0           |

### `jump_fall` Animation

*   **name**: `jump_fall`
*   **frame\_count**: `1`
*   **frame\_width**: `17`
*   **frame\_height**: `17`
*   **frames\_per\_row**: `1`
*   **frame\_wait**: `0.2` seconds per frame.
*   **pos\_x**: `0`
*   **pos\_y**: `52`
*   **shrink\_by\_one\_pixel**: `1`

---