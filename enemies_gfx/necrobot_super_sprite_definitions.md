---
title: Necrobot Super Sprite Definitions
category: enemies_gfx
---

---

# Necrobot Super Sprite Definitions

This document details the sprite and animation definitions for the "Necrobot Super" enemy in Noita, as found in `necrobot_super.xml`.

## Sprite Definition

The main `<Sprite>` tag defines the core visual properties and the primary sprite sheet used for the Necrobot Super.

```xml
<Sprite
 filename="data/enemies_gfx/necrobot_super.png"
 hotspots_filename="data/enemies_gfx/necrobot_hotspots.png"
 offset_x="10"
 offset_y="22"
 default_animation="stand" >
```

### Key Attributes:

*   **`filename`**: Path to the main sprite sheet image (`necrobot_super.png`).
*   **`hotspots_filename`**: Path to the image defining collision/interaction points (`necrobot_hotspots.png`).
*   **`offset_x`**, **`offset_y`**: Adjustments to the sprite's position relative to its entity.
*   **`default_animation`**: The animation to play when the entity first spawns or is idle (`stand`).

## Hotspots

Hotspots define specific interactive or collision points on the sprite.

```xml
	<Hotspot
		color="ff0000"
		name="hand" >
	</Hotspot>
```

### Key Attributes:

*   **`color`**: Defines the color of the hotspot (e.g., `ff0000` for red). This is often used for debugging or specific game logic.
*   **`name`**: A descriptive name for the hotspot (e.g., `hand`).

## Animations

The `<RectAnimation>` tags define individual animations for the Necrobot Super. Each animation is a sequence of frames extracted from the sprite sheet.

### Animation Table

| Name          | `pos_x` | `pos_y` | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `frames_per_row` | `loop` | Notes                               |
| :------------ | :------ | :------ | :------------ | :------------ | :------------- | :----------- | :--------------- | :----- | :---------------------------------- |
| `stand`       | 0       | 0       | 6             | 20            | 30             | 0.2          | 10               | 1      | Idle animation.                     |
| `walk`        | 0       | 30      | 4             | 20            | 30             | 0.082        | 10               | 1      | Walking animation.                  |
| `run`         | 0       | 30      | 4             | 20            | 30             | 0.082        | 10               | 1      | Copied from `walk`.                 |
| `burn`        | 0       | 30      | 4             | 20            | 30             | 0.06         | 10               | 1      | Copied from `walk`, faster frame.   |
| `jump_up`     | 0       | 60      | 1             | 20            | 30             | 0.082        | 10               | 0      | Single frame for jumping upwards.   |
| `jump_fall`   | 0       | 60      | 1             | 20            | 30             | 0.082        | 10               | 0      | Single frame for falling.           |
| `attack_ranged` | 0       | 150     | 10            | 20            | 30             | 0.09         | 10               | 0      | Ranged attack animation.            |
| `fly_idle`    | 0       | 90      | 4             | 20            | 30             | 0.12         | 10               | 1      | Hovering/idle flying animation.     |
| `fly_move`    | 0       | 120     | 4             | 20            | 30             | 0.09         | 10               | 1      | Moving while flying animation.      |
| `attack`      | 0       | 150     | 10            | 20            | 30             | 0.09         | 10               | 0      | Melee attack animation.             |

### Animation Events

Some animations include `<Event>` tags, which trigger specific game actions at certain frames.

*   **`burn` animation:**
    *   `frame="2"`: Triggers `step` event.
    *   `frame="5"`: Triggers `step` event.
    *   Both events have `probability="1"` and `check_physics_material="1"`.

*   **`jump_up` animation:**
    *   `frame="0"`: Triggers `jump` event with `probability="1"` and `check_physics_material="1"`.

*   **`attack_ranged` animation:**
    *   `frame="5"`: Triggers `shoot_bullet` event with `probability="1"` and `check_physics_material="0"`.

*   **`attack` animation:**
    *   `frame="5"`: Triggers `hit` event with `probability="1"` and `check_physics_material="0"`.

### Key Animation Attributes:

*   **`name`**: The identifier for the animation.
*   **`pos_x`**, **`pos_y`**: The top-left corner coordinates of the animation's frame sequence within the sprite sheet.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: How many frames are laid out horizontally in the sprite sheet for this animation.
*   **`loop`**: `1` for looping animations, `0` for one-shot animations.
*   **`<Event>`**: Defines actions to occur at specific frames.
    *   `name`: The name of the event (e.g., `step`, `jump`, `shoot_bullet`, `hit`).
    *   `frame`: The frame number at which the event occurs.
    *   `probability`: Likelihood of the event triggering.
    *   `check_physics_material`: Whether to check the physics material at the entity's location when the event triggers.