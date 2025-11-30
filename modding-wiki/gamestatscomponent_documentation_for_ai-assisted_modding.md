---
title: GameStatsComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:GameStatsComponent
category: modding-wiki
---

# GameStatsComponent Documentation

This document details the `GameStatsComponent` in Noita, a crucial component for managing and influencing various in-game statistics and player progression. Understanding this component is vital for modders looking to create custom game mechanics, balance existing systems, or implement unique player challenges.

## Overview of GameStatsComponent

The `GameStatsComponent` is responsible for tracking and modifying a wide array of player-related statistics within Noita. These statistics can range from simple counters to complex progression metrics that affect gameplay. Modding this component allows for deep customization of how players interact with and are affected by the game's systems.

## Core Functionality and Usage

The `GameStatsComponent` is typically attached to entities that represent the player or other game-critical elements. It stores and manages numerical values that can be read, written, and modified through Lua scripting.

### Key Concepts

*   **Stats:** These are the individual numerical values tracked by the component. Each stat has a unique identifier.
*   **Modifiers:** External factors or game events can apply modifiers to these stats, temporarily or permanently altering their values.
*   **Progression:** Certain stats are often tied to player progression, unlocking new abilities, items, or challenges as they reach specific thresholds.

### Accessing and Modifying Stats via Lua

You can interact with the `GameStatsComponent` using Lua scripting. The primary way to do this is by getting a reference to the entity that has the component and then accessing its stats.

**Example: Getting a player's current gold**

```lua
-- Assuming 'player' is a reference to the player entity
local stats_component = player.GameStatsComponent
if stats_component then
    local current_gold = stats_component.current_gold
    print("Player has " .. current_gold .. " gold.")
end
```

**Example: Adding gold to the player**

```lua
-- Assuming 'player' is a reference to the player entity
local stats_component = player.GameStatsComponent
if stats_component then
    stats_component.current_gold = stats_component.current_gold + 100
    print("Added 100 gold to the player.")
end
```

**Example: Setting a custom stat**

If you have defined a custom stat (e.g., `my_custom_stat`), you can set it like this:

```lua
-- Assuming 'player' is a reference to the player entity
local stats_component = player.GameStatsComponent
if stats_component then
    stats_component.my_custom_stat = 5
    print("Set my_custom_stat to 5.")
end
```

### Important Notes on Stat Names

Stat names are case-sensitive and must match the internal names used by the game or your mod. Common stats include:

*   `current_gold`
*   `kills`
*   `deaths`
*   `total_damage_dealt`
*   `total_damage_taken`
*   `level`
*   `experience`

Refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) for a comprehensive list of available stats and functions.

## XML Configuration

The `GameStatsComponent` can also be configured and defined within XML files, allowing for the creation of new stats or the modification of existing ones at a foundational level.

### Defining New Stats

You can define new stats within the `GameStatsComponent` definition in an entity's XML.

**Example: Defining a custom stat `my_custom_stat`**

```xml
<Entity tags="player">
    <GameStatsComponent
        my_custom_stat="0"
        ... other stats ...
    >
    </GameStatsComponent>
</Entity>
```

This XML snippet defines a new stat named `my_custom_stat` and initializes it to `0`. This stat can then be accessed and manipulated via Lua as shown in the previous section.

### Modifying Existing Stats

You can also override or modify the default values of existing stats for specific entities.

**Example: Setting a specific entity's kill count**

```xml
<Entity tags="enemy_base">
    <GameStatsComponent
        kills="5"
        ... other stats ...
    >
    </GameStatsComponent>
</Entity>
```

This would initialize any entity with the `enemy_base` tag to have a `kills` stat of `5`.

## Common Modding Use Cases

The `GameStatsComponent` is incredibly versatile for modding. Here are a few common applications:

### 1. Custom Progression Systems

Create unique leveling systems or unlockable content based on player achievements.

*   **Example:** A mod that unlocks new spells after the player accumulates a certain number of kills or deals a specific amount of damage.

### 2. Difficulty Modifiers

Adjust game difficulty by altering player stats or enemy stat caps.

*   **Example:** A mod that increases the `total_damage_taken` for all enemies, making them more vulnerable.

### 3. Achievement Tracking

Implement custom achievements that players can unlock by reaching specific stat milestones.

*   **Example:** An achievement for collecting 10,000 gold, tracked via `current_gold`.

### 4. Resource Management

Introduce new resources or modify existing ones (like gold) to create new gameplay loops.

*   **Example:** A mod that introduces a "mana" stat, consumed by spells and regenerated over time.

## Further Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) - For a complete reference of Lua functions and components.
*   [Entity XML Documentation](https://noita.wiki.gg/wiki/Modding:_Entity_XML) - For understanding how components are defined in XML.