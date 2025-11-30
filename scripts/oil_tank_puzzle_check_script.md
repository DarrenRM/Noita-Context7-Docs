---
title: Oil Tank Puzzle Check Script
category: scripts
---

# Oil Tank Puzzle Check Script

This script defines the behavior for a puzzle element that checks for the presence of a specific material within an area. Upon successful detection, it triggers a reward and cleans up the puzzle entity.

## Key Functions

### `material_area_checker_success(pos_x, pos_y)`

This function is called when the puzzle condition is met.

*   **Parameters:**
    *   `pos_x`: The X-coordinate of the puzzle's location.
    *   `pos_y`: The Y-coordinate of the puzzle's location.

*   **Actions:**
    1.  Retrieves the `entity_id` of the puzzle entity.
    2.  Gets the current transform (position) of the puzzle entity.
    3.  Loads a random chest entity at a position slightly above the puzzle.
    4.  Loads a magical symbol particle emitter at the same position.
    5.  Plays a specific sound effect related to player projectiles.
    6.  Kills the puzzle entity.

## Core Logic

The script relies on an external system (likely a `MaterialAreaChecker` component) to detect the presence of a target material. When this checker confirms the condition, it calls `material_area_checker_success`.

## Key Entities Loaded

*   `data/entities/items/pickup/chest_random.xml`: A random loot chest.
*   `data/entities/particles/image_emitters/magical_symbol.xml`: A visual effect indicating success.

## Key Sounds Played

*   `data/audio/Desktop/projectiles.snd` (with specific event `player_projectiles/crumbling_earth/create`): A sound effect to acknowledge the successful puzzle completion.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions.

---