---
title: Dark Blue Vine Part 4
category: entities
---

---

# Dark Blue Vine Part 4

This document describes the `vine_dark_b_4.xml` entity, which represents a segment of a dark blue vine in Noita.

## Sprite Information

The entity uses a sprite defined by the following attributes:

```xml
<Sprite
 filename="data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

### Animation Details

The sprite has a single animation named "stand":

```xml
<RectAnimation
 name="stand"
 pos_x="12"
 pos_y="0"
 frame_count="1"
 frame_width="4"
 frame_height="3"
 frame_wait="1"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

This animation consists of a single frame (`frame_count="1"`), with a frame size of 4x3 pixels. It is set to loop indefinitely (`loop="1"`). The `pos_x` and `pos_y` indicate the starting position of the animation frames within the sprite sheet.