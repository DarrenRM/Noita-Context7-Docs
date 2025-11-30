---
title: Player Rocket Projectile
category: entities
---

# Player Rocket Projectile

This document describes the `rocket_player.xml` entity, which defines a player-controlled rocket projectile in Noita. It inherits its base functionality from `rocket_tank.xml` and adds specific player-oriented attributes.

## Key Components and Attributes

### Entity Definition

*   **`name`**: `$projectile_default` - A placeholder name, indicating it's a default projectile type.
*   **`tags`**: `projectile_player` - Crucial for identifying this as a projectile fired by the player.

### Base Entity Inheritance

*   **`Base file="data/entities/projectiles/rocket_tank.xml"`**: This indicates that `rocket_player.xml` extends the functionality of `rocket_tank.xml`. Any attributes not explicitly overridden here are inherited from the base file.

### `HomingComponent`

*   **`target_tag="homing_target"`**: This component enables homing behavior for the projectile, allowing it to seek targets tagged with `homing_target`.

### `ProjectileComponent`

*   **`damage="2"`**: The base damage dealt by the rocket projectile itself.
*   **`config_explosion`**:
    *   **`damage="1"`**: The damage dealt by the explosion that occurs when the projectile hits something.

### `AudioComponent`

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound effects for this projectile.
*   **`event_root="player_projectiles/rocket"`**: Defines the root event path within the audio bank for player rocket projectile sounds.