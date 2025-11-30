---
title: Big Fly Ragdoll Sprite Definitions
category: ragdolls
---

# Big Fly Ragdoll Sprite Definitions

This documentation outlines the sprite definitions for the "Big Fly" ragdoll in Noita, as found in `data/ragdolls/bigfly/filenames.txt`. These files specify the individual image components that make up the ragdoll's visual representation when it is in a ragdoll state.

## Key Sprite Components

The following are the primary sprite components for the Big Fly ragdoll:

### Head
- **File:** `data/ragdolls/bigfly/head.png`
- **Description:** The main head sprite for the Big Fly.

### Torso
- **File:** `data/ragdolls/bigfly/torso_right.png`
- **Description:** The right half of the Big Fly's torso.
- **File:** `data/ragdolls/bigfly/torso_left.png`
- **Description:** The left half of the Big Fly's torso.

### Legs
- **File:** `data/ragdolls/bigfly/right_leg.png`
- **Description:** The sprite for the Big Fly's right leg.
- **File:** `data/ragdolls/bigfly/left_leg.png`
- **Description:** The sprite for the Big Fly's left leg.

### Wings
- **File:** `data/ragdolls/bigfly/wing.png`
- **Description:** The sprite for the Big Fly's wing. This likely represents a single wing, and its placement and animation would determine the appearance of both wings.

### Antennae
- **File:** `data/ragdolls/bigfly/right_antenna.png`
- **Description:** The sprite for the Big Fly's right antenna.
- **File:** `data/ragdolls/bigfly/left_antenna.png`
- **Description:** The sprite for the Big Fly's left antenna.

## Usage in Modding

When creating or modifying ragdolls, understanding these sprite definitions is crucial for:

- **Visual Customization:** Replacing or altering these `.png` files allows for complete visual overhauls of the Big Fly's ragdoll appearance.
- **Ragdoll Behavior:** While not directly defined here, the arrangement and attachment points of these sprites in the corresponding `.xml` ragdoll definition file will dictate how the ragdoll behaves physically.
- **Performance:** The resolution and complexity of these sprites can impact game performance.

**Note:** This file only lists the sprite filenames. The actual positioning, physics, and animation of these sprites are defined in separate `.xml` files within the `data/ragdolls/` directory.