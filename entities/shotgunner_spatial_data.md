---
title: Shotgunner Spatial Data
category: entities
---

# Shotgunner Spatial Data

This document describes the spatial data for the Shotgunner enemy in Noita, focusing on its sprite layering and color masking. This information is crucial for understanding how the enemy's visual components are rendered and can be used for AI-assisted modding, particularly in sprite manipulation or animation adjustments.

## Sprite Layering and Color Masking

The `shotgunner_spatial_data.txt` file defines the order and color masks for different parts of the Shotgunner sprite. This allows for specific parts of the sprite to be recolored or manipulated independently.

### Key Components and Their Masks

| Component   | Color Mask (RGBA) | Description                                     |
| :---------- | :---------------- | :---------------------------------------------- |
| `left_foot` | `ffff0000`        | The left foot of the Shotgunner.                |
| `torso`     | `ff00ff00`        | The main body/torso of the Shotgunner.          |
| `right_hand`| `ff0000ff`        | The right hand of the Shotgunner.               |
| `head`      | `ffffff00`        | The head of the Shotgunner.                     |
| `right_foot`| `ff800000`        | The right foot of the Shotgunner.               |

**Note:** The RGBA values represent Red, Green, Blue, and Alpha respectively. `ff` indicates full opacity. The specific color masks are used by the game engine to apply effects or recoloring to these sprite parts.

## Usage in AI-Assisted Modding

Understanding this data allows modders to:

*   **Target specific sprite parts for recoloring:** For example, changing the `head` color without affecting the `torso`.
*   **Create custom animations:** By manipulating the order or visibility of these layered components.
*   **Develop AI that interacts with visual elements:** For instance, an AI that targets weak points based on sprite component identification.
*   **Debug visual glitches:** By understanding how different parts are supposed to be rendered.