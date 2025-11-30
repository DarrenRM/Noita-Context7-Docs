---
title: Generic Perk Registration Script
category: guides
---

-- This file is part of the Noita data repository.
-- It is intended for AI-assisted modding documentation.

-- The original file 'perk_reflect.lua' appears to be a placeholder or example
-- and does not contain specific perk definitions.
-- The provided content is a loop that iterates through 'perk_list' and registers
-- perks using their ID, UI name, UI description, UI icon, and perk icon.
-- This suggests it's a generic perk registration script rather than a definition
-- for a specific perk like "Reflect".

-- Therefore, this file does not contain specific moddable attributes for a perk.
-- It's a utility script for loading perk data.

-- For AI-assisted modding, the relevant information would be in the files
-- that actually define the perks within 'perk_list.lua' or other perk definition files.
-- This specific file is not directly moddable in terms of defining new perk behaviors.
```

---
title: Generic Perk Registration Script
category: scripts
---

# Generic Perk Registration Script

This script demonstrates a common pattern for registering perks in Noita. It iterates through a predefined list of perks and registers each one with the game's perk system.

## Purpose

The primary function of this script is to load and make available all defined perks to the game. It acts as a central point for initializing perk data.

## Key Elements

*   **`dofile( "data/scripts/perks/perk_list.lua" )`**: This line loads the external file containing the definitions of all perks. This is where the actual perk data (IDs, names, descriptions, icons) resides.
*   **`for i,perk in ipairs(perk_list) do ... end`**: This loop iterates over each `perk` object found in the `perk_list` table.
*   **`RegisterPerk(...)`**: This is the core function that registers a perk with the game. It takes the following arguments for each perk:
    *   `perk.id`: A unique identifier for the perk.
    *   `perk.ui_name`: The name of the perk as displayed in the user interface.
    *   `perk.ui_description`: The descriptive text for the perk shown in the UI.
    *   `perk.ui_icon`: The icon asset used for the perk in the UI.
    *   `perk.perk_icon`: Another icon asset, potentially for a different UI context or visual representation.

## Modding Implications

While this script itself is not directly moddable to define new perk *behaviors*, understanding it is crucial for modders:

*   **Perk Definitions**: Modders will need to create or modify entries within `perk_list.lua` (or similar files) to define new perks.
*   **Registration Process**: This script shows how those definitions are then integrated into the game.
*   **UI Elements**: Modders can change the `ui_name`, `ui_description`, and `ui_icon` for existing perks or new perks they define.

## Summary

This script serves as a foundational component for the perk system, ensuring that all defined perks are properly initialized and accessible within the game. Modding efforts related to perks will primarily involve modifying the data loaded by `dofile("data/scripts/perks/perk_list.lua")`.