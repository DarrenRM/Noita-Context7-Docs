---
title: Player Ragdoll Sprite Filenames
category: data/ragdolls/player
---

# Player Ragdoll Sprite Filenames

This document lists the sprite filenames used for the player's ragdoll in Noita. These are typically PNG image files that define the visual appearance of the player's body parts when they are ragdolled.

## Key Sprite Components

The following are the essential sprite components that make up the player's ragdoll:

*   **torso.png**: The main body sprite.
*   **head.png**: The sprite for the player's head.
*   **right\_thigh.png**: The sprite for the player's right thigh.
*   **right\_arm.png**: The sprite for the player's right upper arm and forearm.
*   **right\_hand.png**: The sprite for the player's right hand.
*   **left\_thigh.png**: The sprite for the player's left thigh.
*   **left\_arm.png**: The sprite for the player's left upper arm and forearm.
*   **left\_hand.png**: The sprite for the player's left hand.

## File Structure

The sprites are located within the `data/ragdolls/player/` directory.

```
data/ragdolls/player/
├── torso.png
├── right_thigh.png
├── right_arm.png
├── right_hand.png
├── left_thigh.png
├── left_arm.png
├── left_hand.png
└── head.png
```

## Usage in Modding

When creating mods that alter the player's appearance or ragdoll behavior, these filenames will be referenced in configuration files (e.g., within `data/entities/` or custom script files) to specify which sprites to use. For example, a mod might replace `torso.png` with a custom sprite to change the player's body texture.