---
title: Sun Essence Collector Logic
category: scripts
---

---

# Sun Essence Collector Logic

This script defines the behavior of a "sun" entity that collects and reacts to nearby "essence stones" (waterstone, brimstone, thunderstone, stonestone, poopstone). It dynamically changes its appearance and triggers events based on the types of essences it collects.

## Core Functionality

The script's primary purpose is to:
1.  Detect specific "essence stones" within a radius.
2.  Absorb these stones, adding their essence to the sun's collection.
3.  Visually update the sun's sprite based on the collected essences.
4.  Trigger powerful effects and potentially spawn new sun entities upon collecting a sufficient combination of essences.

## Key Attributes and Elements

### 1. Detection Radius
*   `radius = 56`: Defines the area around the sun entity where it will search for essence stones.

### 2. Essence Stone Detection
The script checks for the presence of specific tagged entities within the detection radius:
*   `"waterstone"`: For Water Essence.
*   `"brimstone"`: For Fire Essence.
*   `"thunderstone"`: For Air Essence.
*   `"stonestone"`: For Earth Essence.
*   `"poopstone"`: For Poop Essence.

### 3. Essence Collection Logic
*   The script uses `string.find` to check if an essence type is already present in the `essences_list` stored in a `VariableStorageComponent`.
*   If an essence is new, it enables corresponding components on the sun entity (e.g., `EntitySetComponentsWithTagEnabled( entity_id, "water", true )`).
*   It updates the sun's sprite (`SpriteComponent`) to reflect the newly added essence.
*   It appends the essence name to the `essences_list`.
*   It triggers a large explosion (`explosion_giga.xml`) and screen shake for visual feedback.
*   Detected essence stones are destroyed (`EntityKill`).

### 4. Visual Progression
*   The sun's sprite changes based on the essences collected. Examples:
    *   Water: `data/props_gfx/sun_small_purple.png`
    *   Fire: `data/props_gfx/sun_small_red.png`
    *   Air: `data/props_gfx/sun_small_blue.png`
    *   Earth: `data/props_gfx/sun_small_green.png`
    *   Poop: `data/props_gfx/sun_small_orange.png`

### 5. Stage Progression and Spawning
*   The script tracks the number of unique essences collected (`found`).
*   It disables stage-specific components (`sunbaby_stage_1`, `sunbaby_stage_2`) as more essences are found.
*   **Ultimate Goal:** When 4 unique non-poop essences are collected:
    *   If Poop essence was *not* collected, it spawns `newsun.xml` and sets the `"progress_sun"` flag.
    *   If Poop essence *was* collected, it spawns `newsun_dark.xml` and sets the `"progress_darksun"` flag.
*   Upon spawning a new sun, it triggers music changes, a large screen shake, another explosion, and destroys the current sun entity.

### 6. Poop Essence Handling
*   The presence of Poop essence is tracked separately (`ohno`).
*   It influences whether a "normal" sun or a "dark" sun is spawned at the end.

### 7. Component Interaction
*   `GetUpdatedEntityID()`: Gets the ID of the current sun entity.
*   `EntityGetTransform()`: Retrieves the position of the entity.
*   `EntityGetInRadiusWithTag()`: Finds entities with specific tags within a radius.
*   `EntityGetFirstComponent()`: Retrieves specific components attached to an entity.
*   `ComponentGetValue2()`: Reads values from components.
*   `ComponentSetValue2()`: Writes values to components.
*   `EntitySetComponentsWithTagEnabled()`: Enables or disables components based on tags.
*   `EntityLoad()`: Spawns new entities.
*   `EntityAddChild()`: Makes one entity a child of another.
*   `EntityKill()`: Destroys an entity.
*   `GameScreenshake()`: Triggers screen shaking.
*   `GamePrintImportant()`: Displays important messages to the player.
*   `AddFlagPersistent()`: Sets a persistent game flag.
*   `GameTriggerMusicFadeOutAndDequeueAll()`: Fades out current music.
*   `GameTriggerMusicEvent()`: Starts a new music event.