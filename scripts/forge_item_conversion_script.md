---
title: Forge Item Conversion Script
category: scripts
---

---

# Forge Item Conversion Script

This script defines the logic for a "forge" building that converts specific items into other items or unlocks new abilities. It checks for nearby entities with designated tags and, if conditions are met, triggers transformations, spawns new entities, and applies persistent flags.

## Key Functionality

The script iterates through several item types and applies conversion rules:

### 1. Leukaluu Conversion

*   **Trigger:** Detects entities with the tag `"leukaluu"` within a 70-unit radius.
*   **Conditions:** The item must be a root entity (not carried).
*   **Sub-conditions:**
    *   If a `"kantele"` entity is also present within the radius, the `"leukaluu"` is converted into `"leukaluu_kantele.xml"`. A magical symbol particle emitter is also spawned.
    *   If no `"kantele"` is present, the `"leukaluu"` is converted into a `"FISH"` item action, and the `"card_unlocked_fish"` flag is persistently added.
*   **Visuals:** An explosion effect is spawned at the item's location.

### 2. Broken Portal Conversion

*   **Trigger:** Detects entities with the tag `"card_summon_portal_broken"` within a 70-unit radius.
*   **Conditions:** The item must be a root entity.
*   **Conversion:** Converts the broken portal into a `"SUMMON_PORTAL"` item action.
*   **Visuals:** An explosion effect is spawned.

### 3. Broken Wand Conversion

*   **Trigger:** Detects entities with the tag `"broken_wand"` within a 70-unit radius.
*   **Conditions:** The item must be a root entity.
*   **Conversion:** Converts the broken wand into a `"wand_level_05_better.xml"` entity.
*   **Visuals:** An explosion effect is spawned.

### 4. Tablet Conversion

*   **Trigger:** Detects entities with the tag `"tablet"` within a 70-unit radius.
*   **Conditions:** The item must be a root entity.
*   **Logic:**
    *   It inspects the `ItemComponent` of the tablet to determine its `item_name`.
    *   Based on specific `item_name` values (e.g., `$booktitle02`, `$booktitle04` through `$booktitle10`), it sets a corresponding `new_desc` for a forged book.
    *   If a `new_desc` is determined, it loads a `"base_forged.xml"` entity.
    *   It then updates the `ItemComponent`, `UIInfoComponent`, and `AbilityComponent` of the forged book with the original `item_name` and the new description.
*   **Visuals:** An explosion effect is spawned.

## Global Effects

*   If any conversions occur (`converted` flag is true), music fades out and a specific dark music event (`"music/oneshot/dark_01"`) is triggered.

## Key Attributes/Elements

*   **`EntityGetInRadiusWithTag(pos_x, pos_y, 70, tag)`:** Detects entities within a specified radius and with a given tag.
*   **`EntityGetRootEntity(id)`:** Checks if an entity is the root entity (not part of another entity like a wand or inventory).
*   **`EntityLoad(filepath, x, y)`:** Spawns a new entity from an XML file at a given position.
*   **`EntityKill(id)`:** Destroys an entity.
*   **`CreateItemActionEntity(action_name, x, y)`:** Creates an entity that triggers a specific game action.
*   **`AddFlagPersistent(flag_name)`:** Adds a flag that persists across game sessions.
*   **`EntityGetComponent(id, component_name)`:** Retrieves components attached to an entity.
*   **`ComponentGetValue(component, value_name)`:** Gets a value from a component.
*   **`ComponentSetValue(component, value_name, value)`:** Sets a value for a component.
*   **`GameTriggerMusicFadeOutAndDequeueAll(fade_time)`:** Fades out and stops all currently playing music.
*   **`GameTriggerMusicEvent(event_name, loop, x, y)`:** Triggers a specific music event.