---
title: Scavenger Glue Emissive Sprite Animations
category: data/enemies_gfx
---

# Scavenger Glue Emissive Sprite Animations

This document details the sprite animations for the "scavenger_glue_emissive" entity in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
	filename="data/enemies_gfx/scavenger_glue_emissive.png"
	offset_x="7"
	offset_y="17"
	default_animation="stand" >
    <!-- Animation definitions go here -->
</Sprite>
```

*   **`filename`**: Path to the sprite sheet image.
*   **`offset_x`, `offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: The animation that plays by default when the entity spawns.

## Key Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### `stand` Animation

The default idle animation.

```xml
<RectAnimation
	name="stand"
	pos_x="0"
	pos_y="0"
	frame_count="8"
	frame_width="22"
	frame_height="19"
	frame_wait="0.12"
	frames_per_row="12"
	loop="1" >
</RectAnimation>
```

*   **`name`**: Identifier for the animation.
*   **`pos_x`, `pos_y`**: Starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: Total number of frames in this animation.
*   **`frame_width`, `frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: `1` for looping, `0` for non-looping.

### `walk` Animation

The animation for when the entity is moving.

```xml
<RectAnimation
	name="walk"
	pos_x="0"
	pos_y="19"
	frame_count="6"
	frame_width="22"
	frame_height="19"
	frame_wait="0.082"
	frames_per_row="12"
	loop="1" >
	<Event frame="2" name="step" probability="1" check_physics_material="1"/>
	<Event frame="5" name="step" probability="1" check_physics_material="1"/>
</RectAnimation>
```

*   **`pos_y="19"`**: This animation starts on the second row of frames in the sprite sheet.
*   **`<Event>`**: Triggers specific game events at certain frames.
    *   `name="step"`: Likely plays a footstep sound.
    *   `probability="1"`: The event always occurs.
    *   `check_physics_material="1"`: The event's behavior might depend on the material the entity is standing on.

### `run` Animation

A duplicate of the `walk` animation, suggesting it might not have a distinct visual representation.

```xml
<RectAnimation
	name="run"
	pos_x="0"
	pos_y="19"
	frame_count="6"
	frame_width="22"
	frame_height="19"
	frame_wait="0.082"
	frames_per_row="12"
	loop="1" >
	<Event frame="2" name="step" probability="1" check_physics_material="1"/>
	<Event frame="5" name="step" probability="1" check_physics_material="1"/>
</RectAnimation>
```

### `burn` Animation

A duplicate of the `walk` animation with a slightly faster `frame_wait`, suggesting a visual effect for being on fire.

```xml
<RectAnimation
	name="burn"
	pos_x="0"
	pos_y="19"
	frame_count="6"
	frame_width="22"
	frame_height="19"
	frame_wait="0.06"
	frames_per_row="12"
	loop="1" >
	<Event frame="2" name="step" probability="1" check_physics_material="1"/>
	<Event frame="5" name="step" probability="1" check_physics_material="1"/>
</RectAnimation>
```

### `attack_ranged` Animation

Animation for performing a ranged attack.

```xml
<RectAnimation
	name="attack_ranged"
	pos_x="0"
	pos_y="38"
	frame_count="10"
	frame_width="22"
	frame_height="19"
	frame_wait="0.07"
	frames_per_row="12"
	loop="0"  >
</RectAnimation>
```

*   **`loop="0"`**: This animation plays only once.

### `attack` Animation

Animation for performing a melee attack.

```xml
<RectAnimation
	name="attack"
	pos_x="0"
	pos_y="95"
	frame_count="5"
	frame_width="22"
	frame_height="19"
	frame_wait="0.09"
	frames_per_row="12"
	loop="0"  >
	<Event frame="3" name="attack_melee" probability="1" check_physics_material="0"/>
	<Event frame="4" name="voc_attack" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **`Event frame="3" name="attack_melee"`**: Triggers the melee attack logic on frame 3.
*   **`Event frame="4" name="voc_attack"`**: Triggers a "vocational" attack on frame 4.

### `fly_idle` Animation

Idle animation when flying.

```xml
<RectAnimation
	name="fly_idle"
	pos_x="0"
	pos_y="57"
	frame_count="8"
	frame_width="22"
	frame_height="19"
	frame_wait="0.12"
	frames_per_row="12"
	loop="1"   >
</RectAnimation>
```

### `fly_move` Animation

Animation for movement while flying.

```xml
<RectAnimation
	name="fly_move"
	pos_x="0"
	pos_y="76"
	frame_count="8"
	frame_width="22"
	frame_height="19"
	frame_wait="0.09"
	frames_per_row="12"
	loop="1"   >
</RectAnimation>
```

## Skipped/Commented Animations

The following animations are commented out and not currently active:

*   `jump_up`
*   `jump_fall`

These would need to be uncommented and potentially adjusted to be used.