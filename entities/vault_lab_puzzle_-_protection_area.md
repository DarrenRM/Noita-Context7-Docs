---
title: Vault Lab Puzzle - Protection Area
category: entities
---

---

# Vault Lab Puzzle - Protection Area

This entity defines a protected area within a vault lab puzzle. It uses a `MaterialAreaCheckerComponent` to detect specific materials within its bounds, triggering a Lua script upon success.

## Key Components and Attributes

### MaterialAreaCheckerComponent

This component is responsible for defining the protected zone and its detection logic.

*   **`area_aabb.min_x`, `area_aabb.max_x`, `area_aabb.min_y`, `area_aabb.max_y`**: Defines the rectangular boundaries of the protected area.
    *   `min_x`: -3
    *   `max_x`: 3
    *   `min_y`: 6
    *   `max_y`: 8
*   **`update_every_x_frame`**: How often the area check is performed.
    *   `update_every_x_frame`: 9
*   **`material`**: The primary material to look for within the area.
    *   `material`: `magic_liquid_protection_all`
*   **`material2`**: A secondary material to look for.
    *   `material2`: `magic_liquid_protection_all`
*   **`look_for_failure`**: Whether to trigger on failure (0 = no).
    *   `look_for_failure`: 0
*   **`kill_after_message`**: Whether to kill the entity after a message is displayed (0 = no).
    *   `kill_after_message`: 0

### LuaComponent

This component links the `MaterialAreaCheckerComponent`'s success to a specific Lua script.

*   **`script_material_area_checker_success`**: The script to execute when the material area check is successful.
    *   `script_material_area_checker_success`: `data/scripts/buildings/vault_lab_puzzle_check.lua`

### PixelSceneComponent

This component handles the visual representation of the entity, particularly its background.

*   **`pixel_scene`**: The primary pixel scene for the entity (empty in this case).
    *   `pixel_scene`: `data/biome_impl/empty.png`
*   **`pixel_scene_visual`**: Visual layer for the pixel scene (empty).
*   **`pixel_scene_background`**: The background image for the protected area.
    *   `pixel_scene_background`: `data/biome_impl/vault/lab_puzzle_protect_background.png`
*   **`background_z_index`**: The Z-order for the background.
    *   `background_z_index`: 35
*   **`offset_x`**: Horizontal offset for the pixel scene.
    *   `offset_x`: -7
*   **`offset_y`**: Vertical offset for the pixel scene.
    *   `offset_y`: -7
*   **`skip_biome_checks`**: Whether to skip biome-specific checks.
    *   `skip_biome_checks`: 1