---
title: Sun Spot Building Logic
category: scripts
---

# Sun Spot Building Logic

This script defines the behavior of a "Sun Spot" building in Noita. It acts as a trigger that, when certain environmental conditions are met within its radius, spawns a special item, a large explosion, and initiates a music change.

## Core Functionality

The primary purpose of this script is to detect specific environmental hazards and react to them.

### Trigger Conditions

The building activates if any of the following conditions are met within a 120-unit radius:

*   **Large Explosions:** More than 5 entities tagged with `"big_explosion"`.
*   **Sea of Lava:** At least 1 entity tagged with `"sea_of_lava"`.
*   **Sky Beams:** At least 1 entity tagged with `"beam_from_sky"`.
*   **Gigantic Nukes:** At least 1 entity tagged with `"nuke_giga"`.

### Actions Upon Trigger

When any of the trigger conditions are met, the following actions occur:

1.  **Spawn Sun Egg:** An item with the path `data/entities/items/pickup/sun/sunegg.xml` is loaded at the building's location.
2.  **Spawn Giga Explosion:** A large explosion effect, `data/entities/projectiles/deck/explosion_giga.xml`, is created at the building's location.
3.  **Destroy Building:** The Sun Spot building entity itself is destroyed (`EntityKill`).
4.  **Music Fade Out:** All currently playing music fades out over 3.0 seconds.
5.  **Play Custom Music:** A specific music track, `"music/oneshot/dark_01"`, is triggered to play.
6.  **Display Important Message:** An important game message is displayed to the player using the keys `$log_new_step` and `$logdesc_new_step`.

## Key Attributes and Elements

*   **`EntityGetInRadiusWithTag`**: This function is crucial for detecting nearby entities with specific tags.
    *   `x`, `y`: The coordinates of the building.
    *   `120`: The radius in which to search for entities.
    *   `"tag"`: The specific tag to search for (e.g., `"big_explosion"`, `"sea_of_lava"`).
*   **`EntityLoad`**: Used to spawn new entities into the game world.
    *   `"path/to/entity.xml"`: The XML file defining the entity to be loaded.
    *   `x`, `y`: The coordinates where the entity should be spawned.
*   **`EntityKill`**: Destroys the specified entity.
*   **`GameTriggerMusicFadeOutAndDequeueAll`**: Manages music transitions by fading out existing tracks.
    *   `3.0`: The duration of the fade-out in seconds.
*   **`GameTriggerMusicEvent`**: Starts a specific music event.
    *   `"music/path/to/track.ogg"`: The identifier for the music track.
    *   `true`: Indicates that the music should play.
    *   `x`, `y`: The position associated with the music event (often used for positional audio).
*   **`GamePrintImportant`**: Displays a significant message to the player.
    *   `"$message_key"`: A localization key for the message text.

## Example Usage (Conceptual)

This script would typically be attached to an entity defined in an XML file, representing the Sun Spot building. The `dofile_once` and `dofile` calls at the beginning ensure that necessary utility and action scripts are loaded.

```lua
-- Example of how this script might be included in an entity XML
-- <Entity name="sun_spot_building">
--     <LuaComponent script_path="data/scripts/buildings/sun/spot_2.lua" />
-- </Entity>
```