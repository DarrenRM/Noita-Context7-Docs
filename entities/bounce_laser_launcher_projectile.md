---
title: Bounce Laser Launcher Projectile
category: entities
---

# Bounce Laser Launcher Projectile

This document describes the configuration for the "Bounce Laser Launcher" projectile entity in Noita, focusing on its AI-assisted modding relevant attributes.

## Entity Configuration

The core of this entity is defined by its components, primarily `LuaComponent` and `AudioComponent`.

### LuaComponent

This component links the projectile to its behavior script.

| Attribute           | Value                                     | Description                                                                 |
| :------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/projectiles/bounce_laser_launch.lua` | Specifies the Lua script that governs the projectile's behavior.            |
| `execute_on_added`  | `1`                                       | Indicates that the script should execute immediately when the projectile is spawned. |

### AudioComponent

This component defines the sound effects associated with the projectile.

| Attribute   | Value                                | Description                                                                 |
| :---------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank`| The audio bank file containing the sound events.                            |
| `event_root`| `player_projectiles/bullet_laser`    | The root event name for the projectile's sounds within the audio bank.      |