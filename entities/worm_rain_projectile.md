---
title: Worm Rain Projectile
category: entities
---

# Worm Rain Projectile

This document describes the `worm_rain.xml` entity, which defines a projectile used in Noita. This projectile is designed to simulate a "worm rain" effect, likely by spawning other entities or effects over time.

## Key Components

### LuaComponent

This component is responsible for the projectile's behavior, driven by an external Lua script.

*   **`script_source_file`**: `data/scripts/projectiles/worm_rain.lua` - Specifies the Lua script that controls the projectile's logic.
*   **`execute_every_n_frame`**: `40` - The script will execute its logic every 40 frames.

### LifetimeComponent

Determines how long the projectile exists before being removed.

*   **`lifetime`**: `400` - The projectile will persist for 400 frames.

### LoadEntitiesComponent

This component is used to spawn other entities at the projectile's location.

*   **`entity_file`**: `data/entities/projectiles/remove_ground.xml` - The entity to be spawned. This suggests the "worm rain" effect might involve removing ground or creating impact effects.
*   **`count.min`**: `1` - At least one `remove_ground.xml` entity will be spawned.
*   **`count.max`**: `1` - A maximum of one `remove_ground.xml` entity will be spawned per execution.
*   **`kill_entity`**: `0` - The projectile itself is not killed immediately after spawning entities.
*   **`timeout_frames`**: `2` - The spawned entities will exist for 2 frames before being removed.