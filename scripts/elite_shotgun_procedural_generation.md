---
title: Elite Shotgun Procedural Generation
category: scripts
---

# Elite Shotgun Procedural Generation

This script defines the procedural generation logic for the "Elite Shotgun" in Noita. It dynamically sets various gun properties, including its name, firing behavior, and reload time, with a chance for a "Legendary" variant.

## Key Attributes and Generation Logic

The script focuses on generating a shotgun-like weapon with a degree of randomness. The core mechanics are influenced by a rarity system, where a "rare" (legendary) version has enhanced properties.

### Rarity System

*   **`is_rare`**: A boolean flag (0 or 1) determined by a 1 in 20 chance (`D(20) == 1`). This flag significantly impacts other generated properties.

### Gun Configuration

The script modifies the `AbilityComponent` of the gun entity.

*   **`actions_per_round`**:
    *   Base: Typically 2.
    *   Rare variant: Can be 3 with a 1 in 3 chance (`is_rare == 1 and D(3) == 1`).
*   **`reload_time`**:
    *   Base: Randomly generated between 40 and 80 (`40 + 5 * D(8)`).
    *   Rare variant: Reduced by 5 to 30 units (`reload - 5 * D(6)`).
*   **`shuffle_deck_when_empty`**:
    *   Rare variant: Set to 0 (no shuffling) with a 1 in 3 chance (`is_rare == 1 and D(3) == 1`).

### Bullet Actions

The script adds a series of `GunAction` components to define the firing pattern.

*   **Primary Actions (Base):**
    *   A 1 in 10 chance (`D(10) == 1`) results in `BURST_3` and four `HEAVY_BULLET` actions.
    *   Otherwise, it uses `SCATTER_3` and three `HEAVY_BULLET` actions.
*   **Additional Bullet Action:**
    *   A 1 in 10 chance (`D(10) == 1`) adds another `HEAVY_BULLET` action.
*   **Rare Variant Bonus:**
    *   If `is_rare` is true, an additional `BURST_3` action is always added.

### Naming Convention

*   **Base Name:** If not a rare variant, the gun's name is randomly selected from a `gun_names` table (if available) and prepended to "Shotgun".
*   **Rare Name:** If `is_rare` is true, the name is prefixed with "Legendary ".

### Visual Properties (Rare Variant)

*   **Light Component:** If the gun is rare, its `LightComponent` is modified:
    *   `update_properties` is set to 1.
    *   Color is set to a purple hue: `r = 128`, `g = 0`, `b = 255`.

```lua
-- Example of how gun actions might be structured (simplified)
-- This is not directly from the script but illustrates the concept
local gun_actions = {
    "BURST_3",
    "HEAVY_BULLET",
    "HEAVY_BULLET",
    "HEAVY_BULLET",
    "HEAVY_BULLET",
    -- ... potentially more actions based on randomness
}

-- Example of a potential gun_names table
local gun_names = {
    "Heavy",
    "Rapid",
    "Scatter",
    "Power",
}
```