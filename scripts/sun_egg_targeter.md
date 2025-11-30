---
title: Sun Egg Targeter
category: scripts
---

---

# Sun Egg Targeter

This script defines the behavior for a "sun egg" building in Noita, specifically its targeting mechanism and win condition.

## Core Functionality

The primary function of this script is to identify and tag nearby entities that can be targeted by the "sun egg." Once a sufficient number of targets have been "claimed," the building triggers a special event.

### Targeting Mechanism

-   **Radius:** The script scans for entities within a radius of 260 units around its position.
-   **Tag Requirement:** It specifically looks for entities with the `"homing_target"` tag.
-   **Exclusion:** Entities already tagged with `"sunegg_target"` are ignored to prevent repeated targeting.
-   **Tagging:** Upon finding a valid, untagged target, the script adds the `"sunegg_target"` tag to it.
-   **Variable Storage:** A `VariableStorageComponent` named `"sunegg_target"` is added to the targeted entity.
-   **Lua Component:** A `LuaComponent` is added to the targeted entity, linking to `spot_3_death.lua` for its death script. This component is set to execute only once (`execute_every_n_frame = "-1"`).

## Win Condition and Event Trigger

The script monitors a kill counter associated with the sun egg building. When this counter reaches a specific threshold, a significant in-game event is triggered.

### Threshold and Event

-   **Kill Threshold:** The building triggers its win condition when the `sunegg_kills` variable reaches or exceeds 100.
-   **Spawning:** Upon reaching the threshold, the script spawns:
    -   `data/entities/items/pickup/sun/sunbaby.xml`
    -   `data/entities/projectiles/deck/explosion_giga.xml`
-   **Building Destruction:** The sun egg building itself is destroyed (`EntityKill(entity_id)`).
-   **Music Event:**
    -   All current music fades out over 3 seconds (`GameTriggerMusicFadeOutAndDequeueAll( 3.0 )`).
    -   A specific music track (`"music/oneshot/dark_01"`) is triggered.
-   **Game Message:** An important game message is displayed to the player using `$log_new_step` and `$logdesc_new_step`.

## Key Components and Variables

-   `entity_id`: The unique identifier for the sun egg building entity.
-   `x`, `y`: The coordinates of the sun egg building.
-   `targets`: A table containing the IDs of entities found within the targeting radius.
-   `variablestorages`: A component that stores variables for an entity.
-   `comp`: A reference to the `VariableStorageComponent` that tracks kills.
-   `kills`: An integer representing the current kill count for the sun egg.