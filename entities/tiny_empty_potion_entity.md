---
title: Tiny Empty Potion Entity
category: entities
---

# Tiny Empty Potion Entity

This entity represents a tiny, empty potion that can be consumed by the player. It has a short lifespan and will disappear after a set duration.

## Key Components

### `CellEaterComponent`

This component defines the entity's ability to "eat" or consume cells.

| Attribute        | Value   | Description                                                              |
| :--------------- | :------ | :----------------------------------------------------------------------- |
| `eat_probability`| `100`   | The probability (0-100) that this entity will eat a cell.                |
| `radius`         | `8`     | The radius within which the entity can eat cells.                        |
| `ignored_material`| `potion_glass_box2d` | Materials that this entity will not eat. This prevents it from consuming its own container. |

### `LifetimeComponent`

This component controls how long the entity exists before being removed from the game.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `10`  | The duration (in seconds) the entity will live. |