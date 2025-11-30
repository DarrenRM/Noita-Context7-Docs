---
title: All Nukes Projectile Configuration
category: entities
---

# All Nukes Projectile Configuration

This document details the configuration for the "All Nukes" projectile entity in Noita, primarily focusing on its behavior and associated components.

## Entity Definition

The core entity is defined with the tag `projectile_player`, indicating it's a projectile fired by the player.

```xml
<Entity tags="projectile_player" >
	<!-- Components follow -->
</Entity>
```

## Key Components

### LuaComponent

This component is responsible for executing custom Lua script logic for the projectile.

*   **`script_source_file`**: Specifies the path to the Lua script that governs the projectile's behavior.
    *   `data/scripts/projectiles/all_nukes.lua`
*   **`execute_every_n_frame`**: Set to `-1`, meaning the script does not execute on a recurring frame basis.
*   **`execute_on_added`**: Set to `1`, indicating the script will execute once when the projectile is first added to the game.

```xml
	<LuaComponent
		script_source_file="data/scripts/projectiles/all_nukes.lua"
		execute_every_n_frame="-1"
		execute_on_added="1"
		>
	</LuaComponent>
```

### LifetimeComponent

This component defines how long the projectile will exist before being removed from the game.

*   **`lifetime`**: The projectile will exist for `2` seconds.

```xml
	<LifetimeComponent
		lifetime="2"
		>
	</LifetimeComponent>
```

### AudioComponent

This component handles the sound effects associated with the projectile.

*   **`file`**: The audio bank file containing the sound events.
    *   `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: The root event name for player projectiles.
    *   `player_projectiles/all_spell`
*   **`set_latest_event_position`**: Set to `1`, meaning the sound event will be positioned at the projectile's latest known location.

```xml
	<AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/all_spell"
      set_latest_event_position="1" >
	</AudioComponent>
```