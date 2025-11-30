---
title: Steel Chest Entity Script
category: scripts
---

# Steel Chest Entity Script

This script defines the behavior for a steel chest entity in Noita, specifically focusing on its interaction when opened or picked up.

## Key Functions

### `on_open( entity_item )`

This function is called when the chest is opened. It triggers several effects:

*   **Persistent Flag:** `AddFlagPersistent( "card_unlocked_everything" )` - This likely unlocks all spell cards for the player.
*   **Item Creation:** `CreateItemActionEntity( "ALL_SPELLS", x, y )` - Creates an entity that grants all spells to the player.
*   **Visual Effect:** `EntityLoad("data/entities/particles/image_emitters/chest_effect.xml", x, y)` - Spawns a particle effect associated with opening the chest.
*   **Music Change:**
    *   `GameTriggerMusicFadeOutAndDequeueAll( 3.0 )` - Fades out and stops all current music over 3 seconds.
    *   `GameTriggerMusicEvent( "music/oneshot/dark_03", true, x, y )` - Starts a specific music track ("dark_03") in a one-shot mode at the chest's location.

### `item_pickup( entity_item, entity_who_picked, name )`

This function is called when the chest entity is picked up by another entity.

*   **Game Message:** `GamePrintImportant( "$log_chest", "" )` - Displays an important game message, likely indicating the chest was found.
*   **Chest Opening Logic:** Calls `on_open( entity_item )` to execute the chest's opening effects.
*   **Entity Destruction:** `EntityKill( entity_item )` - Removes the chest entity from the game after it's picked up.

### `physics_body_modified( is_destroyed )`

This function is called when the physics body of the entity is modified, often when it's destroyed or interacts with physics.

*   **Get Updated Entity:** `local entity_item = GetUpdatedEntityID()` - Retrieves the ID of the entity whose physics body was modified.
*   **Chest Opening Logic:** Calls `on_open( entity_item )` to execute the chest's opening effects.
*   **Disable Item Component:**
    *   `edit_component( entity_item, "ItemComponent", function(comp,vars) ... end)` - Accesses and modifies the `ItemComponent`.
    *   `EntitySetComponentIsEnabled( entity_item, comp, false )` - Disables the `ItemComponent`, likely preventing further item-related interactions.
*   **Entity Destruction:** `EntityKill( entity_item )` - Removes the chest entity from the game.

## Key Attributes/Elements

*   **`on_open` Function:** Central to the chest's functionality, handling item unlocks, visual effects, and music changes.
*   **`item_pickup` Function:** Manages the behavior when the chest is collected.
*   **`physics_body_modified` Function:** Handles interactions related to the chest's physics state.
*   **`AddFlagPersistent("card_unlocked_everything")`:** A significant game-altering effect.
*   **`CreateItemActionEntity("ALL_SPELLS", x, y)`:** Grants all spells to the player.
*   **`EntityLoad("data/entities/particles/image_emitters/chest_effect.xml", x, y)`:** Visual feedback for opening.
*   **Music Triggers:** `GameTriggerMusicFadeOutAndDequeueAll` and `GameTriggerMusicEvent` for dynamic audio changes.
*   **`EntityKill`:** Used to remove the chest after its primary function is complete.