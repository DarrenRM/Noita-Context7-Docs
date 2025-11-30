---
title: Boss Limb Death Behavior
category: entities
---

---

# Boss Limb Death Behavior

This document details the Lua script responsible for handling the death of boss limbs in Noita. It defines the effects and item drops that occur when a boss limb is defeated.

## Core Functionality: `death`

The primary function `death` is triggered when a boss limb entity is destroyed. It handles the visual and gameplay consequences of this event.

### Key Actions:

*   **Entity Identification:** Retrieves the unique ID and position of the dying boss limb.
*   **Conditional Item Drops:** The type and quantity of items dropped depend on the persistent flag `card_unlocked_pyramid`.
    *   If `card_unlocked_pyramid` is **true**, a specific set of randomized spell action entities are dropped.
    *   If `card_unlocked_pyramid` is **false**, a different set of randomized spell action entities are dropped, along with a `heart_fullhp` pickup.
*   **Randomized Item Generation:** Utilizes a predefined list of spell action options (`opts`) and a random number generator to select which items are created.
*   **Persistent Flag Management:** Sets the `card_unlocked_pyramid` flag to true after the death sequence, potentially influencing future gameplay.

### Important Variables and Logic:

*   `entity_id`: The unique identifier for the boss limb entity.
*   `pos_x`, `pos_y`: The world coordinates of the boss limb.
*   `flag_status`: A boolean indicating whether the `card_unlocked_pyramid` flag is currently active.
*   `opts`: A table containing strings representing different types of spell action entities that can be spawned.
    *   `"NOLLA"`
    *   `"DAMAGE_RANDOM"`
    *   `"RANDOM_SPELL"`
    *   `"RANDOM_PROJECTILE"`
    *   `"RANDOM_MODIFIER"`
    *   `"RANDOM_STATIC_PROJECTILE"`
    *   `"DRAW_RANDOM"`
    *   `"DRAW_RANDOM_X3"`
    *   `"DRAW_3_RANDOM"`
*   `rnd`: A variable used to store a randomly selected index from the `opts` table.
*   `CreateItemActionEntity(option, x, y)`: A function that spawns a specific item action entity at the given coordinates.
*   `EntityLoad(filepath, x, y)`: A function that loads and places an entity from a specified XML file at the given coordinates.
*   `AddFlagPersistent(flag_name)`: Sets a persistent flag in the game.
*   `HasFlagPersistent(flag_name)`: Checks if a persistent flag is set.
*   `SetRandomSeed(x, y)`: Seeds the random number generator based on world coordinates.

### Example Item Spawning Logic (Simplified):

```lua
-- If the pyramid card is unlocked
if flag_status then
    -- Spawn 4 randomized spell action entities
    for i=1,4 do
        local rnd = Random( 1, #opts ) -- Pick a random option
        CreateItemActionEntity( opts[rnd], pos_x - 8 * 4 + (i-1) * 16, pos_y ) -- Spawn it
        table.remove( opts, rnd ) -- Remove the used option to avoid duplicates in this loop
    end
else
    -- Spawn 4 randomized spell action entities (different set if card not unlocked)
    for i=1,4 do
        local rnd = Random( 1, #opts )
        CreateItemActionEntity( opts[rnd], pos_x - 8 * 4 + (i-1) * 16, pos_y )
        table.remove( opts, rnd )
    end
    -- Also spawn a full HP heart
    EntityLoad( "data/entities/items/pickup/heart_fullhp.xml",  pos_x, pos_y )
end
```