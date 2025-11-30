---
title: Fungal Disease Perk Logic
category: scripts
---

---

# Fungal Disease Perk Logic

This script defines the behavior for the "Fungal Disease" perk in Noita. It dynamically enables or disables the perk's effects based on the proximity of enemies.

## Core Functionality

The script checks for nearby enemies within a specified radius.

### Key Attributes

*   **`radius`**: Defines the detection range for enemies. In this script, it's set to `64` units.
*   **`targets`**: A table containing entities identified as "enemy" within the `radius`.
*   **`comp`**: Represents the "fungal\_disease" LuaComponent. The script checks if this component is currently active.

## Logic Flow

1.  **Enemy Detection**: The script retrieves the entity's position (`x`, `y`) and searches for entities with the tag "enemy" within the `radius`.
2.  **Component Check**: It then checks if the "fungal\_disease" LuaComponent is already attached and enabled.
3.  **Enable Perk**: If enemies are found (`#targets > 0`) and the "fungal\_disease" component is *not* currently enabled (`comp == nil`), the component is enabled.
4.  **Disable Perk**: If no enemies are found (`#targets == 0`) and the "fungal\_disease" component *is* currently enabled (`comp ~= nil`), the component is disabled.

## Script Dependencies

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/gun/procedural/gun_action_utils.lua`