---
title: Angry Levitation Perk Death Logic
category: scripts
---

# Angry Levitation Perk Death Logic

This script defines the behavior when a player with the "Angry Levitation" perk dies. It primarily focuses on modifying the player's flight mechanics based on how many times this perk has been picked up.

## Core Functionality

The `death` function is triggered upon player death. Its main purpose is to:

1.  **Track Perk Pickups:** It increments a global counter for the "PERK_PICKED_HOVER_BOOST" flag, effectively tracking how many times the Angry Levitation perk has been acquired.
2.  **Modify Flight Mechanics:** Based on the pickup count, it calculates a new maximum flight time and adds a portion of it to the player's current remaining flight time.

## Key Attributes and Elements

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This is the main function executed on player death.

*   **`entity_id`**: The ID of the entity that died (the player).
*   **`pos_x`, `pos_y`**: The player's position at the time of death.
*   **`perk_flag`**: A string constant `"PERK_PICKED_HOVER_BOOST"` used to identify and count this specific perk.
*   **`pickup_count`**: A numerical value representing the total number of times the "PERK_PICKED_HOVER_BOOST" perk has been picked up by the player. This is retrieved from global game variables.

### Flight Time Calculation

The core logic for modifying flight time is as follows:

*   **`player_id`**: The ID of the player entity. This is retrieved by searching for a `VariableStorageComponent` named "angry\_levitation".
*   **`comp`**: The `CharacterDataComponent` of the player, which contains flight-related properties.
*   **`flight`**: The player's current remaining flight time.
*   **`maxflight`**: The player's maximum possible flight time.

The new `maxflight` is calculated using an exponential formula based on `pickup_count`:

```lua
maxflight = 2 ^ pickup_count + ( 2 ^ ( pickup_count - 1 ) )
```

The player's `mFlyingTimeLeft` is then updated:

```lua
flight = math.min( maxflight, flight + 1.2 )
```

This ensures the flight time is capped by the new `maxflight` and increases by a fixed amount (1.2) plus a portion of the new maximum.

### Global Variables

*   **`GlobalsGetValue( perk_flag .. "_PICKUP_COUNT", "0" )`**: Reads the current pickup count for the perk from global game state.
*   **`GlobalsSetValue( perk_flag .. "_PICKUP_COUNT", tostring(pickup_count) )`**: (Implicitly used by `tonumber` and incrementing) This would be used to save the updated pickup count.

### Components Accessed

*   **`VariableStorageComponent`**: Used to store and retrieve custom variables associated with entities, specifically the `player_id` for "angry\_levitation".
*   **`CharacterDataComponent`**: Contains core player attributes, including flight mechanics (`mFlyingTimeLeft`, `fly_time_max`).