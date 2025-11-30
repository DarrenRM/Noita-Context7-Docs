---
title: Egg Worm Item
category: entities
---

# Egg Worm Item

This document details the `egg_worm.xml` entity, which represents the Egg Worm item in Noita. This item, when thrown, explodes and spawns a projectile entity.

## Core Components

The Egg Worm item is defined by several key components that dictate its physical properties, behavior, and interaction within the game.

### `PhysicsBodyComponent`

Manages the physical presence and movement of the item.

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `uid`                     | `1`        | Unique identifier for the physics body.                                     |
| `allow_sleep`             | `1`        | Allows the physics body to enter a sleep state when inactive.               |
| `is_bullet`               | `1`        | Indicates that this physics body can act as a projectile.                   |
| `hax_fix_going_through_ground` | `1`        | A fix to prevent the item from clipping through the ground.                 |

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the item.

| Attribute    | Value                        | Description                                     |
| :----------- | :--------------------------- | :---------------------------------------------- |
| `image_file` | `data/items_gfx/egg_worm.png` | The sprite used for the item's visual.          |
| `material`   | `bone_box2d`                 | The physics material defining its interaction. |

### `PhysicsThrowableComponent`

Enables the item to be thrown.

| Attribute           | Value | Description                               |
| :------------------ | :---- | :---------------------------------------- |
| `max_throw_speed`   | `180` | The maximum speed the item can be thrown. |
| `throw_force_coeff` | `1.5` | Coefficient affecting throw force.        |

### `DamageModelComponent`

Handles damage-related properties of the item.

| Attribute                 | Value   | Description                                                              |
| :------------------------ | :------ | :----------------------------------------------------------------------- |
| `hp`                      | `0.6`   | The hit points of the item.                                              |
| `materials_damage`        | `1`     | Whether the item takes damage from certain materials.                    |
| `materials_that_damage`   | `lava`  | The specific materials that will damage the item.                        |
| `materials_how_much_damage` | `0.001` | The amount of damage taken from specified materials.                     |
| `fire_damage_amount`      | `0.2`   | The amount of fire damage the item can inflict.                          |

### `ExplodeOnDamageComponent`

Defines the explosion behavior when the item is damaged.

| Attribute                       | Value                                 | Description