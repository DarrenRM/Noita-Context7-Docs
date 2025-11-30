---
title: Global Stats
source: https://noita.wiki.gg/wiki/Documentation:GlobalStats
category: modding-wiki
---

# Global Stats

This documentation page details the `GlobalStats` component in Noita, which is crucial for understanding and modifying game-wide statistics and progression. Modders can leverage this information to create custom achievements, track player progress, or alter how certain game-wide metrics influence gameplay.

## GlobalStats Component

The `GlobalStats` component is responsible for managing various global statistics within Noita. These statistics can be accessed and modified through Lua scripting, allowing for dynamic gameplay changes and custom progression systems.

### Accessing and Modifying Global Stats

Global stats are typically accessed and modified using the `GameStats` object in Lua.

**Example:**

```lua
-- Get the current value of a global stat
local current_kills = GameStats.GetStat("kills_wands")

-- Increment a global stat
GameStats.IncrementStat("kills_wands", 1)

-- Set a global stat to a specific value
GameStats.SetStat("kills_spells_cast", 100)
```

### Common Global Stats

While the full list can be extensive and may change with game updates, here are some commonly encountered global stats:

*   **`kills_wands`**: The total number of wands destroyed.
*   **`kills_spells_cast`**: The total number of spells cast.
*   **`kills_enemies`**: The total number of enemies killed.
*   **`kills_bosses`**: The total number of bosses killed.
*   **`gold_collected`**: The total amount of gold collected.
*   **`items_collected`**: The total number of items collected.
*   **`deaths`**: The total number of player deaths.
*   **`levels_completed`**: The number of levels completed.
*   **`fastest_level_time_<level_id>`**: The fastest time to complete a specific level (e.g., `fastest_level_time_0`).
*   **`longest_run_time`**: The longest duration a single run has lasted.

**Note:** The exact names and availability of these stats might vary between Noita versions and official updates. It's always recommended to consult the in-game Lua API or community resources for the most up-to-date information.

### Modifying Global Stats via XML

While Lua is the primary method for dynamic interaction, some global stats can be influenced or initialized through XML definitions, particularly when defining new entities or game mechanics that interact with these stats. However, direct manipulation of existing global stats is predominantly done via Lua.

For more in-depth information on the Lua API, refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).