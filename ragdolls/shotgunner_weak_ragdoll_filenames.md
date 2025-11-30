---
title: Shotgunner Weak Ragdoll Filenames
category: ragdolls
---

---

# Shotgunner Weak Ragdoll Filenames

This document outlines the filenames for the individual sprite components that make up the "shotgunner_weak" ragdoll in Noita. These files are essential for defining the visual appearance and animation of this enemy type when it is in a ragdoll state.

## Key Sprite Components

The following are the primary sprite components for the shotgunner_weak ragdoll:

### Torso
- `data/ragdolls/shotgunner_weak/torso.png`
  - The central body part of the ragdoll.

### Head
- `data/ragdolls/shotgunner_weak/head.png`
  - The head sprite for the ragdoll.

### Gun
- `data/ragdolls/shotgunner_weak/gun.png`
  - The sprite for the shotgun the enemy is holding.

### Limbs
- `data/ragdolls/shotgunner_weak/left_arm.png`
- `data/ragdolls/shotgunner_weak/left_hand.png`
- `data/ragdolls/shotgunner_weak/left_thigh.png`
- `data/ragdolls/shotgunner_weak/left_foot.png`
- `data/ragdolls/shotgunner_weak/right_thigh.png`
- `data/ragdolls/shotgunner_weak/right_foot.png`
  - These files define the various parts of the left and right limbs, including arms, hands, thighs, and feet.

## Usage in Modding

When creating or modifying ragdolls for enemies, you would reference these filenames within the relevant entity or ragdoll configuration files. For example, a ragdoll definition might specify which sprite to use for the "torso" bone. Understanding these filenames allows modders to:

- **Replace existing sprites:** Swap out the default sprites with custom artwork.
- **Create new ragdoll variations:** Define new ragdoll behaviors by assigning different sprite components.
- **Debug ragdoll issues:** Identify if a visual problem is related to a specific sprite file.