---
title: Slow Bullets Effect Entity
category: entities
---

# Slow Bullets Effect Entity

This entity defines a persistent effect that slows down projectiles.

## Core Components

### LuaComponent
This component is responsible for the actual logic of slowing bullets.

*   **`script_source_file`**: `data/scripts/projectiles/effect_slow_bullets.lua` - Specifies the Lua script that handles the effect's behavior.
*   **`execute_every_n_frame`**: `3` - The script will be executed every 3 frames, allowing for continuous effect application.

### LifetimeComponent
Determines how long the effect will persist.

*   **`lifetime`**: `3600` - The effect will last for 3600 frames (approximately 1 minute).

### InheritTransformComponent
This component is present but has no configurable attributes in this specific entity. It typically handles the entity's position and transformation.