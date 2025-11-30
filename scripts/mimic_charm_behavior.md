---
title: Mimic Charm Behavior
category: scripts
---

---

# Mimic Charm Behavior

This script defines the behavior of a Mimic when it is "charmed" by the player. When charmed, the Mimic will periodically drop various items for the player.

## Core Logic

The script checks if the entity has the "CHARM" game effect. If it does, it proceeds with the following logic:

1.  **Proximity Check:** It finds the closest player unit and checks if the Mimic is within a certain range (approximately 75 units horizontally and 35 units vertically above the player).
2.  **Item Dropping:** If the player is close enough, the Mimic will attempt to drop an item.
3.  **Poop Counter:** A counter (`mimic_poop_count`) is maintained within the Mimic's `VariableStorageComponent`. This counter increments each time an item is dropped.
4.  **Item Selection:** The item dropped is determined by a random chance, with higher chances for gold nuggets and lower chances for rarer items like hearts or potions.
5.  **Projectile Firing:** The selected item is fired as a projectile towards the player's general direction.
6.  **Exhaustion Mechanic:** If the `mimic_poop_count` reaches 10 or more, there's a small chance (1 in 9) that the Mimic will inflict self-damage and potentially die from exhaustion.

## Key Attributes & Elements

*   **`CHARM` Game Effect:** The primary trigger for this script's execution.
*   **`VariableStorageComponent`:** Used to store and increment the `mimic_poop_count`.
*   **Proximity Thresholds:**
    *   Horizontal: `dist_x < 75`
    *   Vertical: `dist_y > 0 and dist_y < 35` (player must be above the mimic)
*   **Item Drop Probabilities:**
    *   `heart.xml`: `rnd >= 1000` (effectively 0% chance in current logic, likely a typo in source)
    *   `potion.xml`: `rnd >= 985`
    *   `goldnugget_200.xml`: `rnd >= 925`
    *   `goldnugget_50.xml`: `rnd >= 800`
    *   `goldnugget_10.xml`: Default/fallback
*   **Projectile Velocity:** Calculated based on the direction towards the player, with randomized magnitude and occasional horizontal reversal.
*   **Exhaustion Trigger:** `poop_count >= 10`
*   **Exhaustion Chance:** `Random( 1, 9 ) == 9` (1/9 chance)
*   **Self-Damage on Exhaustion:** `EntityInflictDamage( entity_id, 1000, "DAMAGE_PROJECTILE", "", "NONE", 0, 0 )`

## Example Item Drop Logic (Simplified)

```lua
-- Inside the proximity check:
local gift_entity = "data/entities/items/pickup/goldnugget_10.xml" -- Default

local rnd = Random( 1, 1000 )

if( rnd >= 1000 ) then -- Note: This condition is unlikely to be met with Random(1, 1000)
    gift_entity = "data/entities/items/pickup/heart.xml"
elseif( rnd >= 985 ) then
    gift_entity = "data/entities/items/pickup/potion.xml"
elseif( rnd >= 925 ) then
    gift_entity = "data/entities/items/pickup/goldnugget_200.xml"
elseif( rnd >= 800 ) then
    gift_entity = "data/entities/items/pickup/goldnugget_50.xml"
end

-- The selected gift_entity is then spawned.
```

## Potential Modding Areas

*   **Item Drop Pool:** Modify the `gift_entity` paths and their associated random chances to change what items the Mimic drops.
*   **Drop Frequency:** Adjust the `mimic_poop_count` thresholds and the exhaustion chance.
*   **Proximity Ranges:** Alter the `dist_x` and `dist_y` values to change how close the player needs to be.
*   **Projectile Behavior:** Modify the velocity calculations for `vel_x` and `vel_y`.
*   **Exhaustion Damage:** Change the amount of damage inflicted upon exhaustion.