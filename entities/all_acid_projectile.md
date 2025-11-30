---
title: All Acid Projectile
category: entities
---

---

# All Acid Projectile

This document describes the "All Acid" projectile entity in Noita, focusing on its key attributes for AI-assisted modding.

## Entity Definition

The `all_acid.xml` file defines a player-owned projectile with specific behaviors and components.

```xml
<Entity tags="projectile_player" >
	<!-- ... components ... -->
</Entity>
```

### Key Attributes:

*   **`tags="projectile_player"`**: Identifies this entity as a projectile originating from the player.

## Components

### LuaComponent

This component governs the projectile's dynamic behavior through a Lua script.

```xml
<LuaComponent
	script_source_file="data/scripts/projectiles/all_acid.lua"
	execute_every_n_frame="-1"
	execute_on_added="1"
	>
</LuaComponent>
```

#### Key Attributes:

*   **`script_source_file="data/scripts/projectiles/all_acid.lua"`**: Specifies the Lua script responsible for the projectile's logic.
*   **`execute_on_added="1"`**: Indicates that the script's `on_added` function should be executed when the projectile is spawned.

### LifetimeComponent

This component controls how long the projectile exists before being removed.

```xml
<LifetimeComponent
	lifetime="2"
	>
</LifetimeComponent>
```

#### Key Attributes:

*   **`lifetime="2"`**: The projectile will exist for 2 seconds.

### AudioComponent

This component handles the sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="player_projectiles/all_spell"
  set_latest_event_position="1" >
</AudioComponent>
```

#### Key Attributes:

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the projectile's sounds.
*   **`event_root="player_projectiles/all_spell"`**: The root event name for the projectile's sound effects.
*   **`set_latest_event_position="1"`**: Ensures the sound plays at the projectile's current position.