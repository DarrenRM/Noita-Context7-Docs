---
title: Necromancer Sprite Animations
category: data/enemies_gfx/
---

# Necromancer Sprite Animations

This document details the sprite animations for the Necromancer enemy in Noita, as defined in `necromancer.xml`. It focuses on the key attributes of the sprite and its associated animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the Necromancer.

### Key Attributes:

*   **filename**: `data/enemies_gfx/necromancer.png` - The path to the sprite sheet image.
*   **offset\_x**: `15` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `22` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The Necromancer has several distinct animations, each defined by a `<RectAnimation>` tag.

### Common Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.

### Defined Animations:

| Animation Name   | Frame Count | Frame Size (WxH) | Frame Wait (s) | Frames Per Row | Loop | Notes                               |
| :--------------- | :---------- | :--------------- | :------------- | :------------- | :--- | :---------------------------------- |
| **stand**        | 6           | 30x30            | 0.1            | 7              | Yes  | Idle animation.                     |
| **walk**         | 6           | 30x30            | 0.085          | 7              | Yes  | Walking animation.                  |
| **run**          | 6           | 30x30            | 0.085          | 7              | Yes  | Running animation.                  |
| **burn**         | 6           | 30x30            | 0.085          | 7              | Yes  | Burning effect animation.           |
| **fly\_idle**    | 6           | 30x30            | 0.12           | 7              | Yes  | Flying idle animation.              |
| **fly\_move**    | 6           | 30x30            | 0.12           | 7              | Yes  | Flying movement animation.          |
| **attack\_ranged** | 7           | 30x30            | 0.08           | 7              | No   | Ranged attack animation.            |
| **attack**       | 7           | 30x30            | 0.08           | 7              | No   | Melee/general attack animation.     |

## Animation Events

Animations can trigger specific game events at certain frames.

### `attack_ranged` and `attack` Events:

Both the `attack_ranged` and `attack` animations have a single event defined:

*   **name**: `"shoot_magic"`
*   **frame**: `5` - The event triggers on the 5th frame of the animation.
*   **probability**: `1` - The event is guaranteed to trigger.
*   **max\_distance**: `500` - Maximum distance for the event's effect.
*   **on\_finished**: `0` - Indicates the event does not wait for the animation to finish.
*   **check\_physics\_material**: `0` - Physics material is not checked for this event.

This event is responsible for the Necromancer firing its magical projectiles.