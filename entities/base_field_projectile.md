---
title: Base Field Projectile
category: entities
---

# Base Field Projectile

This document details the `base_field.xml` entity, which serves as a foundational projectile for various field effects in Noita. It's designed to be highly customizable and often acts as a template for more specialized projectiles.

## Core Components

This projectile utilizes several key components to define its behavior and appearance.

### SpriteComponent

Defines the visual representation of the projectile.

| Attribute      | Description                                                                 |
| :------------- | :-------------------------------------------------------------------------- |
| `_enabled`     | Whether the component is active (1 for enabled, 0 for disabled).            |
| `offset_x`     | Horizontal offset of the sprite.                                            |
| `offset_y`     | Vertical offset of the sprite.                                              |
| `alpha`        | Transparency of the sprite (0.0 to 1.0).                                    |
| `image_file`   | Path to the sprite image file (e.g., `data/projectiles_gfx/blast.xml`). |
| `additive`     | Whether the sprite uses additive blending (1 for enabled, 0 for disabled).  |

### VelocityComponent

Governs the projectile's movement and physical properties.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `gravity_y` | The amount of gravity affecting the projectile on the Y-axis. |
| `mass`    | The mass of the projectile.                     |

### LifetimeComponent

Determines how long the projectile exists before being removed.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `lifetime`| The duration in frames the projectile will exist. |

### SpriteParticleEmitterComponent

Responsible for emitting particles from the projectile.

| Attribute                 | Description