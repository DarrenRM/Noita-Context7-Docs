---
title: Gold Orb Greed Drop Behavior
category: scripts
---

# Gold Orb Greed Drop Behavior

This script defines the behavior of the "Gold Orb Greed" item when it is kicked or dropped. It determines what kind of loot or effect is generated based on how many times the orb has been "kicked" (interacted with).

## Core Functionality

The primary function `drop()` is called when the entity is interacted with. It uses a `VariableStorageComponent` named "kick_count" to track the number of interactions.

### Loot Generation Logic

The script generates different outcomes based on the `count` of kicks:

*   **First Kick (`count == 1`):** Always results in a specific outcome (outcome 10).
*   **Subsequent Kicks (`count > 3`):** The probability of rarer outcomes decreases.
*   **Random Outcomes:** A random number between 1 and 21 is generated to determine the outcome.

### Specific Outcomes

*   **Outcome 1:** Spawns a "giga explosion" projectile and destroys the orb.
*   **Outcome 20:** Shoots a single `bloodmoney_1000` pickup.
*   **Outcome 15:** Shoots two `bloodmoney_200` pickups.
*   **Outcomes < 10:** Shoots a single `bloodmoney_50` pickup.
*   **Other Outcomes (including 10):** Shoots four `bloodmoney_10` pickups in a cross pattern.

## Key Components and Functions

*   **`drop()` function:** The main logic for determining the loot/effect.
*   **`kick()` function:** A simple alias that calls the `drop()` function.
*   **`GetUpdatedEntityID()`:** Retrieves the ID of the entity being interacted with.
*   **`EntityGetTransform( entity_id )`:** Gets the position (x, y) of the entity.
*   **`EntityGetFirstComponent( entity_id, "VariableStorageComponent", "kick_count" )`:** Retrieves the "kick\_count" variable storage component.
*   **`ComponentGetValue2( comp, "value_int" )`:** Gets the integer value from a component.
*   **`ComponentSetValue2( comp, "value_int", count )`:** Sets the integer value of a component.
*   **`SetRandomSeed( ... )`:** Initializes the random number generator for predictable (within the same frame/seed) randomness.
*   **`Random( min, max )`:** Generates a random integer within the specified range.
*   **`EntityLoad( xml_path, x, y )`:** Loads an entity from an XML file at a given position.
*   **`EntityKill( entity_id )`:** Destroys the specified entity.
*   **`shoot_projectile( caster_entity_id, projectile_xml_path, x, y, velocity_x, velocity_y )`:** Shoots a projectile from a specified entity.

## Example Usage (Conceptual)

To modify the drop behavior:

1.  **Adjust `outcome` ranges:** Change the `if/elseif` conditions to alter which outcomes trigger which effects.
2.  **Modify `count` thresholds:** Alter the `count == 1` or `count > 3` conditions to change how the kick count affects probabilities.
3.  **Change spawned entities:** Replace the `EntityLoad` or `shoot_projectile` calls with different item or projectile XML paths.
4.  **Alter loot quantities:** Modify the number of `shoot_projectile` calls for specific outcomes.

```lua
-- Example: To make the giga explosion more likely on the 5th kick
if ( count == 5 ) then
    outcome = 1 -- Make outcome 1 more probable
elseif ( count > 3 ) then
    outcome = math.max( 1, outcome - ( count - 2 ) )
end
```