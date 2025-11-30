---
title: Quantum Split Projectile
category: entities
---

# Quantum Split Projectile

This entity defines a projectile that utilizes a Lua script to perform a "quantum split" effect.

## Key Components

### LuaComponent
This component is responsible for the projectile's behavior.

*   **`script_source_file`**: `data/scripts/projectiles/quantum_split.lua`
    *   Specifies the Lua script that governs the projectile's logic.
*   **`execute_every_n_frame`**: `3`
    *   The script will be executed every 3 frames.
*   **`remove_after_executed`**: `1`
    *   The projectile entity will be removed from the game after the script has executed.

This setup indicates that the `quantum_split.lua` script handles the core functionality of this projectile, including its creation, behavior, and eventual removal.