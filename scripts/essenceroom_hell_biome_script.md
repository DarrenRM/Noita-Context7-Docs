---
title: Essenceroom Hell Biome Script
category: scripts
---

---

# Essenceroom Hell Biome Script

This script defines the behavior and spawning logic for the "Essenceroom Hell" biome in Noita. It focuses on loading specific pixel scenes and spawning essence pickups.

## Core Functionality

### `init(x, y, w, h)`
This function is called when the biome is initialized. It loads the visual and background elements for the Essenceroom.

- **Pixel Scene:** `data/biome_impl/essenceroom.png`
- **Visual Scene:** `data/biome_impl/essenceroom_visual.png`
- **Background:** `data/biome_impl/essenceroom_background_with_diamond.png` (with `true` indicating it's a background layer)

### `spawn_essence(x, y)`
This function is responsible for spawning essence pickups within the biome.

- **Entity Spawned:** `data/entities/items/pickup/essence_water.xml`

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation, indicating they are either placeholders for future development or not utilized in this specific biome script.

- `spawn_small_enemies`
- `spawn_big_enemies`
- `spawn_items`
- `spawn_props`
- `spawn_props2`
- `spawn_props3`
- `spawn_lamp`
- `load_pixel_scene`
- `load_pixel_scene2`
- `spawn_unique_enemy`
- `spawn_unique_enemy2`
- `spawn_unique_enemy3`
- `spawn_ghostlamp`
- `spawn_candles`
- `spawn_potions`
- `spawn_wands`
- `spawn_orb`

## Constants

- `CHEST_LEVEL = 3`: This constant likely influences the type or rarity of chests that can spawn in this biome, though no chest spawning logic is present in this script.

## Dependencies

This script relies on several helper files:

- `data/scripts/director_helpers.lua`
- `data/scripts/biome_scripts.lua`
- `data/scripts/lib/utilities.lua`