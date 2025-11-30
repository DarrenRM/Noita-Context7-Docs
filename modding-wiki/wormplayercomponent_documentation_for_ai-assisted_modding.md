---
title: WormPlayerComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:WormPlayerComponent
category: modding-wiki
---

# WormPlayerComponent Documentation

This document details the `WormPlayerComponent` in Noita, a crucial component for understanding and modifying player worm behavior. Modders can leverage this information to alter how player worms interact with the game world, their abilities, and their overall mechanics.

## Understanding WormPlayerComponent

The `WormPlayerComponent` is a core entity component in Noita that governs the player's worm. It manages various aspects of the worm's state and behavior, making it a primary target for modding efforts related to player mechanics.

### Key Properties and Functionality

While the original wiki page had no specific text detailing the properties, in a typical Noita modding context, a component like `WormPlayerComponent` would likely manage:

*   **Movement and Physics:** How the worm moves, its speed, acceleration, and interaction with gravity.
*   **Health and Damage:** The worm's hit points, damage resistance, and how it takes damage.
*   **Abilities and Actions:** What actions the player worm can perform, such as attacking, using items, or special abilities.
*   **State Management:** Tracking the worm's current status (e.g., alive, dead, stunned, poisoned).
*   **Interaction with Game Systems:** How the worm interacts with other entities, environmental hazards, and game events.

### Modding Implications

Modifying or extending the functionality of `WormPlayerComponent` can lead to a wide range of gameplay changes, including:

*   **New Player Abilities:** Granting the player worm unique skills or powers.
*   **Altered Movement Mechanics:** Changing how fast or agile the player worm is.
*   **Customizable Health and Defense:** Adjusting player survivability.
*   **Unique Interactions:** Creating new ways for the player worm to interact with the environment or enemies.

## Data Tables and References

*(Note: The original source page contained no specific data tables, code examples, or reference lists for `WormPlayerComponent`. If such content were present, it would be formatted here. For example, if there were a table of enum values related to worm states, it would appear below.)*

### Example: Hypothetical Worm State Enum

If `WormPlayerComponent` had associated enum values for its state, they might be presented like this:

| Enum Name      | Value | Description                               |
| :------------- | :---- | :---------------------------------------- |
| `WORM_STATE_IDLE` | 0     | The worm is not performing any action.    |
| `WORM_STATE_MOVING` | 1     | The worm is actively moving.              |
| `WORM_STATE_ATTACKING` | 2     | The worm is performing an attack.         |
| `WORM_STATE_DEAD` | 3     | The worm has been defeated.               |

### Example: Hypothetical Property Definitions

If specific properties were documented, they might look like this:

*   **`max_health`**: (float) The maximum health points the worm can have.
*   **`movement_speed`**: (float) The base speed at which the worm moves.
*   **`damage_multiplier`**: (float) A multiplier applied to all damage dealt by the worm.

## Code Examples

*(Note: The original source page contained no code examples for `WormPlayerComponent`. If code snippets demonstrating its use or modification were available, they would be included here with appropriate language tags.)*

### Example: Hypothetical Lua Script for Modifying Worm Speed

```lua
-- Example: Increase player worm movement speed by 20%
local worm_component = GetPlayerWorm():GetComponent("WormPlayerComponent")
if worm_component then
    worm_component.movement_speed = worm_component.movement_speed * 1.20
end
```

### Example: Hypothetical XML Component Definition

If `WormPlayerComponent` were defined in an XML file, it might look something like this:

```xml
<components>
    <WormPlayerComponent
        max_health="100.0"
        movement_speed="50.0"
        damage_multiplier="1.0"
    />
</components>
```

## Related Links

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity Components](https://noita.wiki.gg/wiki/Modding:_Entity_Components)