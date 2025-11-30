---
title: Flamer Ragdoll Sprites
category: ragdolls
---

# Flamer Ragdoll Sprites

This documentation describes the sprite assets used for the "Flamer" enemy's ragdoll in Noita. These files define the visual components of the ragdoll when the enemy is defeated.

## Sprite Files

The following PNG files are used to construct the Flamer's ragdoll:

*   `torso.png`: The main body of the Flamer.
*   `head.png`: The head of the Flamer.
*   `left_foot.png`: The left foot of the Flamer.
*   `right_foot.png`: The right foot of the Flamer.
*   `tanks.png`: The fuel tanks attached to the Flamer.
*   `gun.png`: The flamethrower weapon carried by the Flamer.

## Usage

These sprite files are referenced by the game's entity definitions and ragdoll system. When a Flamer entity is destroyed, its ragdoll is spawned, and these images are used to render the individual pieces of the ragdoll in the game world.

## Modding Considerations

When creating custom ragdolls or modifying existing ones, ensure that the sprite files are correctly named and placed within the appropriate `data/ragdolls/[entity_name]/` directory. The game expects specific filenames for each body part.