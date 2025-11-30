---
title: Sentry Target Entity
category: entities
---

# Sentry Target Entity

This entity defines a basic target for sentries, primarily used for testing and debugging. It's a simple, stationary object with a hitbox and a visual representation.

## Key Components

### `HitboxComponent`

Defines the collision area for the entity.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x` | -2    | Minimum X-axis extent of the hitbox.      |
| `aabb_max_x` | 2     | Maximum X-axis extent of the hitbox.      |
| `aabb_min_y` | -2    | Minimum Y-axis extent of the hitbox.      |
| `aabb_max_y` | 2     | Maximum Y-axis extent of the hitbox.      |

### `InheritTransformComponent`

Allows the entity to inherit transformations, specifically its position.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `only_position` | 1     | Only inherits position, not rotation/scale. |

#### `Transform` (within `InheritTransformComponent`)

Specifies the relative position of the entity.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `position.x` | 0     | X-coordinate offset.                      |
| `position.y` | -8    | Y-coordinate offset.                      |

### `GenomeDataComponent`

Provides basic genetic information, though not heavily utilized for this specific entity.

| Attribute         | Value | Description                               |
| :---------------- | :---- | :---------------------------------------- |
| `herd_id`         | target | Identifier for its herd.                  |
| `food_chain_rank` | 20    | Rank in the food chain.                   |
| `is_predator`     | 0     | Indicates if it's a predator (0 = no).    |

### `SpriteComponent`

Defines the visual appearance of the entity.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/projectiles_gfx/target.xml` | Path to the sprite's image file.          |
| `emissive`  | 1                                   | Makes the sprite emit light (1 = yes).    |

### `LifetimeComponent`

Determines how long the entity exists before despawning.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime` | 1200  | Duration in frames (20 seconds at 60 FPS). |

## Tags

The entity is assigned the following tags:

*   `mortal`: Can be killed.
*   `prey`: Can be targeted by predators.
*   `sentry_target`: Specifically designated as a target for sentries.