---
title: Wizard Hand Sprite Definitions
category: entities
---

# Wizard Hand Sprite Definitions

This document details the sprite definitions for the "Wizard Hand" entity in Noita, focusing on its visual animations and associated events.

## Sprite Definition

The primary `<Sprite>` tag defines the base image and default animation for the Wizard Hand.

### Key Attributes

*   **filename**: `data/entities/animals/boss_wizard/wizard_hand.png` - The path to the sprite sheet.
*   **offset\_x**: `40` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `56` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The Wizard Hand utilizes several `RectAnimation` tags to define its various visual states. Each animation specifies frame details and timing.

### Common Animation Attributes

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; `1` (or omitted) indicates it loops.

### Defined Animations

| Animation Name   | Frame Count | Frame Wait | Loop | Notes                                     |
| :--------------- | :---------- | :--------- | :--- | :---------------------------------------- |
| `stand`          | 6           | 0.14       | Yes  | Idle standing animation.                  |
| `walk`           | 6           | 0.12       | Yes  | Walking animation.                        |
| `run`            | 6           | 0.10       | Yes  | Running animation.                        |
| `burn`           | 6           | 0.09       | Yes  | Burning animation.                        |
| `fly_idle`       | 6           | 0.11       | Yes  | Idle flying animation.                    |
| `fly_move`       | 6           | 0.09       | Yes  | Moving while flying animation.            |
| `attack`         | 6           | 0.06       | No   | Melee attack animation.                   |
| `attack_ranged`  | 18          | 0.05       | No   | Ranged attack animation.                  |
| `attack_ranged2` | 11          | 0.06       | No   | Alternative ranged attack animation.      |

## Animation Events

Specific frames within animations can trigger events.

### Key Event Attributes

*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **name**: The name of the event to trigger (e.g., `attack_melee`, `attack_shoot`).
*   **on\_finished**: `0` means the event triggers at the specified frame; `1` means it triggers when the animation finishes.
*   **probability**: The chance (0-1) of the event occurring.
*   **max\_distance**: Relevant for attack events, defining the effective range.

### Event Examples

*   **`attack` animation**:
    *   At frame `7`, triggers `attack_melee` with a probability of `1` and a `max_distance` of `500`.
*   **`attack_ranged` animation**:
    *   At frame `11`, triggers `attack_shoot` with a probability of `1` and a `max_distance` of `500`.
*   **`attack_ranged2` animation**:
    *   At frame `7`, triggers `attack_shoot` with a probability of `1` and a `max_distance` of `500`.