---
title: Sun Egg Item
category: entities
---

# Sun Egg Item

This document describes the `sunegg.xml` entity, which represents a "Sun Egg" item in Noita. This item is a projectile that deals significant damage and has various environmental effects.

## Core Functionality

The Sun Egg is a projectile with a variety of damaging and material-altering effects. It's designed to be a potent offensive tool.

### Key Components

*   **`PhysicsBodyComponent`**: Defines the physical properties of the egg, allowing it to interact with the game world as a projectile.
*   **`PhysicsImageShapeComponent`**: Assigns the visual appearance of the egg, using `normals_orb_56_noise.png` and a `gem_box2d_yellow_sun` material.
*   **`SpriteComponent`**: Handles the visual rendering of the egg, including its `fog_of_war_hole` effect.
*   **`UIInfoComponent`**: Provides basic information for UI elements, such as the item name (`$item_seed_b`).
*   **`MagicConvertMaterialComponent`**: This is a crucial component, responsible for transforming various materials into lava. It has multiple instances targeting different material tags like `[liquid_common]`, `[sand_ground]`, and `[sand_other]`. It also has a general instance that ignites materials.
*   **`CellEaterComponent`**: Allows the egg to consume certain materials within its radius, preventing it from being consumed itself.
*   **`AreaDamageComponent`**: Multiple instances of this component define the damaging aura of the egg at different radii and with varying damage types (Curse, Explosion, Fire).
*   **`ParticleEmitterComponent`**: Generates yellow sparks around the egg, contributing to its visual effect.
*   **`LuaComponent`**: Executes a script (`spot_3.lua`) that likely handles more complex behaviors or interactions.
*   **`VariableStorageComponent`**: Stores a kill counter for the sun egg.
*   **`AudioLoopComponent`**: Plays a looping sound effect associated with the sun.
*   **`CameraBoundComponent`**: Manages how the item interacts with the camera's bounds.

## Key Attributes and Elements

### `PhysicsImageShapeComponent`

| Attribute      | Value                               | Description                                                              |
| :------------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `image_file`   | `data/items_gfx/normals_orb_56_noise.png` | The texture file used for the egg's visual representation.               |
| `material`     | `gem_box2d_yellow_sun`              | The physics material applied to the egg.                                 |

### `MagicConvertMaterialComponent` (Examples)

| Attribute           | Value                               | Description