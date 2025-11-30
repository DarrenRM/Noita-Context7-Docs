---
title: Root Grower Fruit Sprite
category: guides
---

<?xml version="1.0" encoding="UTF-8"?>
<Sprite
 filename="data/props_gfx/root_grower_fruit.png"
 offset_x="9"
 offset_y="11"
 default_animation="grow" >

 <RectAnimation
  name="grow"
  pos_x="0"
  pos_y="0"
  frame_count="8"
  frame_width="18"
  frame_height="18"
  frame_wait="0.1"
  frames_per_row="8"
  loop="0" >
 </RectAnimation>

</Sprite>
```

---
title: Root Grower Fruit Sprite
category: props_gfx
---

# Root Grower Fruit Sprite

This documentation describes the sprite definition for the "root_grower_fruit" in Noita. It details the visual representation and animation of this prop.

## Sprite Definition

The main `<Sprite>` element defines the visual asset and its default animation.

### Key Attributes:

*   **filename**: `data/props_gfx/root_grower_fruit.png` - Specifies the path to the sprite image file.
*   **offset\_x**: `9` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `11` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"grow"` - The name of the animation to play by default.

## Animations

The `<Sprite>` element contains one or more animation definitions.

### `grow` Animation

This animation defines the visual sequence for the root grower fruit's growth.

#### Key Attributes:

*   **name**: `"grow"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `8` - The total number of frames in this animation.
*   **frame\_width**: `18` - The width of each individual frame.
*   **frame\_height**: `18` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).