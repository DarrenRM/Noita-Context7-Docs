---
title: Laser Shooter Sprite Animations
category: entities_gfx
---

# Laser Shooter Sprite Animations

This document details the sprite animations for the "lasershooter" enemy in Noita, focusing on its visual representation and attack behaviors.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offsets.

### Key Attributes:

*   **filename**: `data/enemies_gfx/lasershooter.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `12` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` elements, each defining a distinct animation.

### Common Animation Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The starting X-coordinate of the animation frames on the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames on the sprite sheet.

### Defined Animations:

| Name            | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Other Attributes                               |
| :-------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :--------------------------------------------- |
| **stand**       | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                                                |
| **walk**        | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                                                |
| **run**         | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                                                |
| **burn**        | 4           | 20          | 24           | 6              | 0.23       | 0     | 1     |                                                |
| **attack\_ranged** | 12          | 21          | 25           | 12             | 0.08       | 0     | 26    | `loop="0"`, `shrink_by_one_pixel="1"` |

## Attack Animation Events

The `attack_ranged` animation includes specific `<Event>` tags that trigger actions during the animation sequence.

### Key Event Attributes:

*   **name**: The name of the event (e.g., "voc\_shoot", "shoot\_laser").
*   **frame**: The animation frame number at which the event occurs.
*   **probability**: The chance of the event occurring (1 means always).
*   **max\_distance**: The maximum distance at which the event can trigger.
*   **on\_finished**: Whether the event should trigger when the animation finishes (0 means no).
*   **check\_physics\_material**: Whether to check physics materials (0 means no).

### Defined Events for `attack_ranged`:

| Event Name    | Frame | Probability | Max Distance | On Finished | Check Physics Material |
| :------------ | :---- | :---------- | :----------- | :---------- | :--------------------- |
| **voc\_shoot** | 1     | 1           | 300          | 0           | 0                      |
| **shoot\_laser** | 8     | 1           | 500          | 0           | 0                      |