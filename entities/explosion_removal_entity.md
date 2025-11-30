---
title: Explosion Removal Entity
category: entities
---

# Explosion Removal Entity

This entity is a simple, non-visual entity designed to trigger a Lua script for removing explosions. It's a lightweight way to manage explosion cleanup without needing a visible sprite or complex physics.

## Key Components

### LuaComponent

This is the core of the entity, responsible for executing the associated Lua script.

*   **`script_source_file`**: Specifies the path to the Lua script to be executed.
    *   Value: `data/scripts/projectiles/explosion_remove.lua`
*   **`execute_every_n_frame`**: Determines how often the script is executed.
    *   Value: `1` (Executes every frame)
*   **`remove_after_executed`**: Controls whether the entity is removed after the script has been executed.
    *   Value: `1` (Entity is removed after execution)

## Purpose

The primary purpose of this entity is to act as a trigger for the `explosion_remove.lua` script. This script likely handles the cleanup and removal of explosion effects and their associated data from the game world, preventing lingering visual artifacts or performance issues.

## Usage

This entity is typically spawned by other game events or entities that create explosions. It's designed to be a one-time use component that cleans up after itself.