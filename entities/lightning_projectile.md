---
title: Lightning Projectile
category: entities
---

# Lightning Projectile

This document details the configuration of the "Lightning" projectile entity in Noita, focusing on its core attributes for AI-assisted modding.

## Entity Definition

The `lightning.xml` file defines a player-owned projectile with the `projectile_type` set to `LIGHTNING`.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... -->
</Entity>
```

## Key Components and Attributes

### ProjectileComponent

This component governs the fundamental behavior of the projectile.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `lifetime`                | Duration the projectile exists before expiring (2 seconds).                 |
| `projectile_type`         | Specifies the projectile's type as `LIGHTNING`.                             |
| `muzzle_flash_file`       | Particle effect for the muzzle flash (`muzzle_flash_laser.xml`).            |
| `damage`                  | Base damage of the projectile (0). Damage is handled by `damage_by_type`. |
| `shoot_light_flash_r`     | Red component of the shooting light flash (190).                            |
| `shoot_light_flash_g`     | Green component of the shooting light flash (248).                          |
| `shoot_light_flash_b`     | Blue component of the shooting light flash (255).                           |
| `shoot_light_flash_radius`| Radius of the shooting light flash (208).                                   |

#### `damage_by_type`

Defines damage dealt based on type.

| Type        | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `electricity` | 1.0   | Deals 1.0 damage of type electricity.     |

### LightningComponent

This component specifically handles the electrical nature and explosion effects of the lightning projectile.

| Attribute        | Description