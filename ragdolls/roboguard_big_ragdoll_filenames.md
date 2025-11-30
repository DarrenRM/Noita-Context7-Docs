---
title: Roboguard Big Ragdoll Filenames
category: ragdolls
---

```

# Roboguard Big Ragdoll Filenames

This document lists the filenames for the individual sprite components of the "Roboguard Big" enemy's ragdoll. These files are used to construct the visual representation of the enemy when it is defeated and its body breaks apart.

## Sprite Components

The following files define the visual assets for each part of the Roboguard Big's ragdoll:

| Part Name     | Filename                               | Description                               |
|---------------|----------------------------------------|-------------------------------------------|
| Torso         | `data/ragdolls/roboguard_big/torso.png`  | The main body segment of the ragdoll.     |
| Right Thigh   | `data/ragdolls/roboguard_big/right_thigh.png` | The upper part of the right leg.          |
| Right Foot    | `data/ragdolls/roboguard_big/right_foot.png`  | The foot of the right leg.                |
| Right Shoulder| `data/ragdolls/roboguard_big/right_shoulder.png`| The shoulder joint of the right arm.      |
| Right Arm     | `data/ragdolls/roboguard_big/right_arm.png`   | The upper arm segment of the right arm.   |
| Right Hand    | `data/ragdolls/roboguard_big/right_hand.png`  | The hand of the right arm.                |
| Left Thigh    | `data/ragdolls/roboguard_big/left_thigh.png`  | The upper part of the left leg.           |
| Left Foot     | `data/ragdolls/roboguard_big/left_foot.png`   | The foot of the left leg.                 |
| Cord 1        | `data/ragdolls/roboguard_big/cord_1.png`      | A visual component representing a cord.   |
| Cord 2        | `data/ragdolls/roboguard_big/cord_2.png`      | Another visual component representing a cord.|

## Usage

These `.png` files are referenced by the game's ragdoll system to assemble the visual appearance of the "Roboguard Big" enemy when its physics simulation results in a broken state. Each file corresponds to a specific body part or accessory, allowing for a fragmented and dynamic death animation.