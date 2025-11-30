---
title: Dragon Spot Entity
category: scripts
---

# Dragon Spot Entity

This script defines the behavior for a "Dragon Spot" entity in Noita. When triggered, it spawns a boss dragon and a magical symbol particle effect, then destroys itself.

## Key Functionality

### `collision_trigger()`

This function is executed when the entity is triggered (e.g., by collision).

*   **Spawns Boss Dragon:** Loads `data/entities/animals/boss_dragon.xml` at the current entity's position.
*   **Spawns Magical Symbol:** Loads `data/entities/particles/image_emitters/magical_symbol_fast.xml` at the current entity's position.
*   **Configures Boss Dragon:** Attaches a `LuaComponent` to the spawned boss dragon.
    *   `script_death`: Sets the death script to `data/scripts/animals/boss_dragon_death.lua`.
    *   `execute_every_n_frame`: Set to `"-1"`, indicating no regular frame execution.
*   **Destroys Self:** Removes the "Dragon Spot" entity using `EntityKill()`.

## Lua Component Configuration

The `LuaComponent` added to the spawned boss dragon is configured as follows:

```lua
{
	script_death = "data/scripts/animals/boss_dragon_death.lua",
	execute_every_n_frame = "-1",
}
```