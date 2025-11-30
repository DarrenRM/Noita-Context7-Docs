---
title: Tank Ragdoll Sprites
category: ragdolls
---

# Tank Ragdoll Sprites

This documentation describes the sprite assets used for the "tank" ragdoll in Noita. These sprites define the visual components of the tank's ragdoll when it is destroyed or interacts with the environment.

## Sprite Files

The following PNG files are used to construct the tank ragdoll:

*   `gun.png`: Likely represents the weapon or turret component of the tank.
*   `strut.png`: Suggests structural elements or supports for the tank.
*   `base.png`: The primary body or chassis of the tank.
*   `cord1.png`: One of the cord or cable assets.
*   `cord2.png`: Another cord or cable asset, potentially for a different connection or effect.

## Usage

These sprite files are referenced by the game's ragdoll system to render the visual representation of the tank when it breaks apart. Each sprite typically corresponds to a distinct physical part of the tank that can be simulated independently in the ragdoll physics.

## Key Attributes (Implied)

While the raw data only provides filenames, the game engine would interpret these sprites with attributes such as:

*   **Position:** Where each sprite is anchored relative to the ragdoll's center.
*   **Rotation:** The default orientation of each sprite.
*   **Collision Shape:** The physics shape associated with each sprite for interaction.
*   **Layer/Depth:** The rendering order of sprites.
*   **Material Properties:** How the sprite interacts with liquids, fire, etc. (though this is more likely defined in separate material files).