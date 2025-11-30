---
title: Fire Miner Sprite and Animations
category: data/enemies_gfx
---

# Fire Miner Sprite and Animations

This document details the sprite and animation definitions for the Fire Miner enemy in Noita, as defined in `miner_fire.xml`.

## Sprite Definition

The main sprite definition for the Fire Miner.

```xml
<Sprite 
  filename="data/enemies_gfx/miner_fire.png"
  hotspots_filename="data/enemies_gfx/miner_fire_hotspots.png"
  offset_x="7" 
  offset_y="14"
  default_animation="stand" >
  
  <Hotspot 
    color="ff0000" 
    name="hand" >
  </Hotspot>
  
</Sprite>
```

### Key Attributes:

*   **filename**: Path to the main sprite texture.
*   **hotspots_filename**: Path to the texture defining collision/interaction points.
*   **offset_x, offset_y**: Adjusts the sprite's position relative to its origin.
*   **default_animation**: The animation to play when the entity is idle or no other animation is specified.
*   **Hotspot**: Defines specific points on the sprite, such as "hand" for interactions.

## Animations

The Fire Miner has several distinct animations, each defined by a `RectAnimation` tag. These animations are typically arranged in a grid on the sprite sheet.

### `stand` Animation

The default idle animation.

*   **frame\_count**: 6
*   **frame\_height**: 18
*   **frame\_wait**: 0.2 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 6
*   **name**: "stand"
*   **pos\_x, pos\_y**: 0, 0 (Indicates the starting position of this animation's frames on the sprite sheet)

### `attack` Animation

Used for melee attacks.

*   **frame\_count**: 7
*   **frame\_height**: 18
*   **frame\_wait**: 0.05 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **loop**: 0 (Does not loop)
*   **name**: "attack"
*   **pos\_x, pos\_y**: 0, 90

#### Events:

*   **frame 4**: Triggers `hit` and `voc_attack` events.

### `attack_ranged` Animation

Used for ranged attacks.

*   **frame\_count**: 7
*   **frame\_height**: 18
*   **frame\_wait**: 0.12 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **loop**: 0 (Does not loop)
*   **name**: "attack_ranged"
*   **pos\_x, pos\_y**: 0, 90

#### Events:

*   **frame 4**: Triggers `throw_release` and `throw` events.

### `walk` Animation

Standard walking animation.

*   **frame\_count**: 6
*   **frame\_height**: 18
*   **frame\_wait**: 0.11 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 6
*   **name**: "walk"
*   **pos\_x, pos\_y**: 0, 18

#### Events:

*   **frame 1 & 4**: Triggers `step` events.

### `run` Animation

Faster movement animation.

*   **frame\_count**: 6
*   **frame\_height**: 18
*   **frame\_wait**: 0.1 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **name**: "run"
*   **pos\_x, pos\_y**: 0, 18

#### Events:

*   **frame 1 & 4**: Triggers `step` events.

### `jump_up` Animation

Animation for jumping upwards.

*   **frame\_count**: 2
*   **frame\_height**: 18
*   **frame\_wait**: 0.09 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **loop**: 0 (Does not loop)
*   **name**: "jump_up"
*   **pos\_x, pos\_y**: 0, 36

#### Events:

*   **frame 0**: Triggers `jump` event.

### `alert` Animation

An animation for when the miner is alerted.

*   **frame\_count**: 2
*   **frame\_height**: 18
*   **frame\_wait**: 0.09 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **loop**: 0 (Does not loop)
*   **name**: "alert"
*   **pos\_x, pos\_y**: 0, 72

### `burn` Animation

Animation for when the miner is on fire.

*   **frame\_count**: 6
*   **frame\_height**: 18
*   **frame\_wait**: 0.09 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **name**: "burn"
*   **pos\_x, pos\_y**: 0, 18

#### Events:

*   **frame 1 & 4**: Triggers `step` events.

### `jump_fall` Animation

Animation for falling after a jump.

*   **frame\_count**: 3
*   **frame\_height**: 18
*   **frame\_wait**: 0.09 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **loop**: 0 (Does not loop)
*   **name**: "jump_fall"
*   **pos\_x, pos\_y**: 0, 54

### `land` Animation

Animation played upon landing.

*   **frame\_count**: 2
*   **frame\_height**: 18
*   **frame\_wait**: 0.08 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **loop**: 0 (Does not loop)
*   **name**: "land"
*   **pos\_x, pos\_y**: 0, 72

#### Events:

*   **frame 0**: Triggers `land` event.

### `swim_idle` Animation

Idle animation when swimming.

*   **frame\_count**: 6
*   **frame\_height**: 18
*   **frame\_wait**: 0.085 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **name**: "swim_idle"
*   **pos\_x, pos\_y**: 0, 18

#### Events:

*   **frame 1 & 4**: Triggers `paddle` events.

### `swim_move` Animation

Movement animation when swimming.

*   **frame\_count**: 6
*   **frame\_height**: 18
*   **frame\_wait**: 0.08 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **name**: "swim_move"
*   **pos\_x, pos\_y**: 0, 18

#### Events:

*   **frame 1 & 4**: Triggers `paddle` events.

### `jump_prepare` Animation

Animation for preparing to jump.

*   **frame\_count**: 3
*   **frame\_height**: 18
*   **frame\_wait**: 0.08 seconds per frame
*   **frame\_width**: 18
*   **frames\_per\_row**: 8
*   **loop**: 0 (Does not loop)
*   **name**: "jump_prepare"
*   **pos\_x, pos\_y**: 0, 108

#### Events:

*   **frame 0**: Triggers `voc_jump` event.
*   **frame 2**: Triggers `jump_start` event.