---
title: Disable Healing in Meat Biome
category: scripts
---

---

# Disable Healing in Meat Biome

This script modifies player behavior when entering the "$biome_meat" biome. It disables healing effects for the player entity if the "BOSS_MEAT_DEAD" global variable is not set to "1".

## Core Functionality

The script utilizes the `biome_entered` function, which is triggered whenever the player transitions between biomes.

### `biome_entered( new_biome_name, old_biome_name )`

This function checks the `new_biome_name` and a global game state variable to determine whether to enable or disable a specific component on the player entity.

#### Key Logic:

1.  **Biome Check:** It verifies if the `new_biome_name` is exactly "$biome_meat".
2.  **Boss Status Check:** It checks the global variable `BOSS_MEAT_DEAD`. If this variable is "0" (meaning the boss is alive), the healing restriction is applied.
3.  **Component Toggling:**
    *   If both conditions are met (player is in the meat biome and the boss is alive), the component with the tag `"effect_no_heal_in_meat_biome"` is enabled on the player entity.
    *   Otherwise, the component is disabled.

## Relevant Components

*   **`effect_no_heal_in_meat_biome`**: This is a tag used to identify a component that, when enabled, prevents healing effects from functioning. The specific implementation of this component is assumed to be defined elsewhere in the game's data.

## Global Variables

*   **`BOSS_MEAT_DEAD`**: A global variable that tracks the status of the meat biome boss. A value of "0" indicates the boss is alive, while "1" signifies the boss has been defeated.

## Example Usage

When a player enters the "$biome_meat" biome while the meat boss is still alive, the `effect_no_heal_in_meat_biome` component will be activated on the player, preventing any healing. Upon leaving the biome or defeating the boss, this effect will be removed.