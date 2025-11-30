---
title: Altar Tablet Magic Script
category: scripts
---

---

# Altar Tablet Magic Script

This script handles various "rain" effects and transformations that occur when specific entities are interacted with or collected by the player near an altar. It checks for the presence of certain tagged entities, their proximity to the player, and then triggers corresponding events.

## Core Functionality

The script primarily focuses on detecting and reacting to the following entity types:

*   **Chests:** Triggers a "chest rain" effect.
*   **Utility Boxes:** Triggers a "utility rain" effect.
*   **Sunrocks (`sunrock`):** Spawns a `newsun.xml` item.
*   **Dark Sunrocks (`darksunrock`):** Spawns a `newsun_dark.xml` item.
*   **Greed Crystals (`greed_crystal`):** Spawns a "greed rain" effect, with variations based on a global flag.
*   **Worm Crystals (`worm_crystal`):** Spawns a "worm rain" effect.
*   **Hand Statues (`statue_hand`):** Spawns multiple drone enemies with monk arms.
*   **Tablets (`tablet`):** Transforms tablets into gold and tracks how many have been "eaten" to potentially spawn gazer enemies.
*   **Helpless Animals (`helpless_animal`):** Triggers a "fish rain" effect if they have a `AdvancedFishAIComponent`.
*   **Mimic Potions (`mimic_potion`):** Triggers a "mimic potion rain" effect.

## Key Mechanics

### Proximity Detection

Most effects are triggered when the player is within a certain radius of the target entity. The script calculates the Manhattan distance (`math.abs(x - cx) + math.abs(y - cy)`) for this.

### Global Flags and Persistence

Many of these effects are designed to occur only once per game session or save. This is managed using `GlobalsSetValue` and `AddFlagPersistent`. Once an effect is triggered, a corresponding global variable is set to "1", preventing the effect from repeating.

### Player Interaction

The script generally requires a player to be present and within range to trigger the effects. It identifies the player using `EntityGetTag("player_unit")`.

### Entity Spawning and Transformation

*   **Spawning:** New entities are loaded using `EntityLoad` at specific locations, often relative to the player's position.
*   **Transformation:** Tablets are converted to gold using `EntityConvertToMaterial`.
*   **Destruction:** Triggered entities are usually destroyed using `EntityKill`.

## Specific Effect Details

### Chest Rain

*   **Trigger:** Player within 48 units of a "chest" entity.
*   **Effect:** Spawns `data/entities/misc/chest_rain.xml` and `data/entities/particles/image_emitters/chest_effect.xml`.
*   **Persistence:** `MISC_CHEST_RAIN` global flag.

### Utility Rain

*   **Trigger:** Player within 48 units of a "utility\_box" entity.
*   **Effect:** Spawns `data/entities/misc/utility_rain.xml` and `data/entities/particles/image_emitters/chest_effect.xml`.
*   **Persistence:** `MISC_UTIL_RAIN` global flag.

### Sun Effects

*   **Trigger:** Player within 72 units of a "sunrock" or "darksunrock" entity.
*   **Effect:** Spawns `data/entities/items/pickup/sun/newsun.xml` or `data/entities/items/pickup/sun/newsun_dark.xml`, respectively, along with `chest_effect.xml`.
*   **Persistence:** `MISC_SUN_EFFECT` and `MISC_DARKSUN_EFFECT` global flags.

### Greed Crystal Rain

*   **Trigger:** Player within 64 units of a "greed\_crystal" entity.
*   **Effect:** Spawns either `greed_rain.xml` or `greed_rain_simple.xml` based on the `MISC_GREED_RAIN` global flag. Also spawns `chest_effect.xml`.
*   **Persistence:** `MISC_GREED_RAIN` global flag.

### Worm Crystal Rain

*   **Trigger:** Player within 64 units of a "worm\_crystal" entity.
*   **Effect:** Spawns `data/entities/misc/worm_rain.xml`.
*   **Persistence:** `misc_worm_rain` persistent flag.

### Hand Statue Effect

*   **Trigger:** Player within 64 units of a "statue\_hand" entity.
*   **Effect:** Spawns 12 "drone\_lasership.xml" entities with "monk\_arms\_standalone.xml" attached in a circular formation. The statue is destroyed and replaced with an FX entity.
*   **Persistence:** `misc_monk_bots` persistent flag.

### Tablet Transformation

*   **Trigger:** Player within 56 units of a "tablet" entity.
*   **Effect:** Transforms the tablet into gold (`"gold"` material), spawns `chest_effect.xml`, and increments a `tablets_eaten` counter stored in a `VariableStorageComponent`.
*   **Monster Spawn:** If `tablets_eaten` exceeds 2, there's a chance (based on a random roll) to spawn 3 "gazer.xml" entities.
*   **Persistence:** `misc_altar_tablet` persistent flag.

### Fish Rain

*   **Trigger:** Player within 64 units of a "helpless\_animal" entity that has an `AdvancedFishAIComponent`.
*   **Effect:** Spawns `data/entities/misc/fish_rain.xml` and `chest_effect.xml`.
*   **Persistence:** `MISC_FISH_RAIN` global flag.

### Potion Mimic Rain

*   **Trigger:** Player within 64 units of a "mimic\_potion" entity that is alive (has `mimic_liquid` material) and not a child of another entity.
*   **Effect:** Spawns `data/entities/misc/mimic_potion_rain.xml` (potentially with a "mimic\_potion\_sky" tag) and `chest_effect.xml`.
*   **Persistence:** `MISC_MIMIC_POTION_RAIN` global flag.