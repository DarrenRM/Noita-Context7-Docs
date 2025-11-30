---
title: PlayerStatsComponent
source: https://noita.wiki.gg/wiki/Documentation:PlayerStatsComponent
category: modding-wiki
---

# PlayerStatsComponent

This documentation page details the `PlayerStatsComponent` in Noita, a crucial component for understanding and modifying player statistics. Modders will find this information essential for altering player health, mana, stamina, and other core attributes, enabling custom gameplay mechanics and challenges.

## Overview

The `PlayerStatsComponent` is responsible for managing the player's core statistics. These statistics are fundamental to gameplay and can be directly manipulated by mods to create unique player experiences.

## Component Structure

The `PlayerStatsComponent` is defined within the game's entity system. Its properties dictate various player attributes.

### Key Properties

The following are some of the key properties managed by the `PlayerStatsComponent`:

*   **Health:** The player's current and maximum health.
*   **Mana:** The player's current and maximum mana.
*   **Stamina:** The player's current and maximum stamina.
*   **Oxygen:** The player's current and maximum oxygen levels.
*   **Gold:** The amount of gold the player possesses.
*   **Experience:** The player's current experience points.
*   **Level:** The player's current level.

## Modifying Player Stats

Mods can interact with the `PlayerStatsComponent` to alter these statistics. This is typically done through Lua scripting.

### Example: Increasing Max Health

This Lua code snippet demonstrates how to increase the player's maximum health by 50.

```lua
-- Get the player entity
local player = Game.GetPlayer()

-- Get the PlayerStatsComponent
local stats_component = player.GetComponent(PlayerStatsComponent)

if stats_component then
    -- Increase max health by 50
    stats_component.max_health = stats_component.max_health + 50
    -- Optionally, heal the player to the new max health
    stats_component.health = stats_component.max_health
end
```

### Example: Restoring Mana

This example shows how to fully restore the player's mana.

```lua
-- Get the player entity
local player = Game.GetPlayer()

-- Get the PlayerStatsComponent
local stats_component = player.GetComponent(PlayerStatsComponent)

if stats_component then
    -- Restore mana to maximum
    stats_component.mana = stats_component.max_mana
end
```

## Related Components and Concepts

*   **Entity System:** The `PlayerStatsComponent` is part of Noita's entity-component system. Understanding this system is crucial for effective modding.
*   **Lua API:** For more advanced interactions and access to game functions, refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).

## Further Information

For a comprehensive understanding of Noita's modding capabilities, consult the main [Modding Documentation](https://noita.wiki.gg/wiki/Modding_Documentation).