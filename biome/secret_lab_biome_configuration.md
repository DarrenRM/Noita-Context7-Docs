---
title: Secret Lab Biome Configuration
category: biome
---

---

# Secret Lab Biome Configuration

This document outlines the configuration for the "Secret Lab" biome in Noita, focusing on its core elements for AI-assisted modding.

## Core Biome Loading

The `init` function is responsible for loading the visual and structural components of the Secret Lab biome.

### `init(x, y, w, h)`

*   **Purpose:** Initializes the Secret Lab biome at the specified coordinates.
*   **Key Attributes:**
    *   `LoadPixelScene`: This is the primary function for defining the biome's appearance and layout.
        *   `"data/biome_impl/secret_lab.png"`: Defines the pixel-based structure and collision data of the biome.
        *   `"data/biome_impl/secret_lab_visual.png"`: Defines the visual layer, including textures and decorative elements.
        *   `"data/biome_impl/secret_lab_background.png"`: Specifies the background image for the biome.
        *   `true`: Indicates that the biome should be loaded with parallax scrolling.

## Entity Spawning (Conceptual)

While the provided code snippet focuses on biome loading, it includes numerous commented-out or empty functions that represent potential entity spawning points. These are crucial for defining the biome's inhabitants and interactive elements.

### `RegisterSpawnFunction`

*   **Purpose:** Registers the `init` function to be called during biome generation.
*   **Key Attributes:**
    *   `0xffffeedd`: A unique identifier for the spawn function.
    *   `"init"`: The name of the function to be registered.

### Placeholder Spawn Functions

The following functions are defined but empty or commented out in the provided snippet. In a complete biome definition, these would be populated with `EntityLoad` calls to place specific entities.

*   `spawn_small_enemies(x, y)`: For spawning smaller enemy types.
*   `spawn_big_enemies(x, y)`: For spawning larger or more formidable enemies.
*   `spawn_items(x, y)`: For placing various items, such as consumables or crafting materials.
*   `spawn_props(x, y)`, `spawn_props2(x, y)`, `spawn_props3(x, y)`: For spawning environmental props and decorations.
*   `spawn_lamp(x, y)`: For placing light sources.
*   `load_pixel_scene(x, y)`, `load_pixel_scene2(x, y)`: Potentially for loading additional pixel-based scene elements.
*   `spawn_unique_enemy(x, y)`, `spawn_unique_enemy2(x, y)`, `spawn_unique_enemy3(x, y)`: For spawning unique or boss-like enemies.
*   `spawn_ghostlamp(x, y)`: For spawning specific types of lamps.
*   `spawn_candles(x, y)`: For placing candles.
*   `spawn_potions(x, y)`: For placing potion items.
*   `spawn_wands(x, y)`: For placing wands.

## Special Entity Spawning (`spawn_orb`)

This function is specifically designed to spawn a key entity within the Secret Lab.

### `spawn_orb(x, y)`

*   **Purpose:** Spawns a significant entity, likely a boss or a major encounter, within the biome.
*   **Key Attributes:**
    *   `EntityLoad("data/entities/animals/boss_alchemist/boss_alchemist.xml", x + 20, y)`: This is the primary entity loaded. It indicates the presence of the "Boss Alchemist" within the Secret Lab.
    *   Commented-out lines suggest potential for spawning books or music energy entities, which could be part of the boss encounter or environmental storytelling.

## Key Takeaways for Modding

*   **Biome Structure:** The `LoadPixelScene` function is central to defining the biome's physical layout and visual appearance. Modifiers can alter the `.png` files to change the biome's geometry and aesthetics.
*   **Entity Placement:** The numerous `spawn_` functions, even if currently placeholders, represent the framework for populating the biome with enemies, items, and environmental objects. Modders can implement these functions to introduce custom entities or modify existing spawn behaviors.
*   **Boss Encounters:** The `spawn_orb` function highlights how specific, high-impact entities are integrated. Modifying this function allows for changes to boss encounters or the introduction of new unique enemies.
*   **Dependencies:** The biome relies on helper scripts like `director_helpers.lua`, `biome_scripts.lua`, and `utilities.lua` for its functionality. Ensure these are available or compatible with your modifications.