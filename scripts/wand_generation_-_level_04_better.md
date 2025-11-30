---
title: Wand Generation - Level 04 (Better)
category: guides
---

--[[
This script generates a wand with specific properties.
It leverages the `gun_procedural_better.lua` script for its generation logic.
The `generate_gun` function is called with the following parameters:
- 80: Likely represents a base spell count or power level.
- 4: Could indicate the number of spell slots or a similar structural parameter.
- false: A boolean flag, its exact meaning depends on the `generate_gun` implementation (e.g., disabling a specific feature).
]]
```

---
title: Wand Generation - Level 04 (Better)
category: scripts/gun/procedural
---

# Wand Generation - Level 04 (Better)

This script defines a procedural wand generation for Noita, specifically targeting a "better" quality at level 04. It utilizes a shared procedural generation script to create the wand's properties.

## Key Generation Parameters

The `generate_gun` function is the core of this script. It's called with specific arguments that influence the resulting wand:

*   **Base Power/Spell Count:** `80` - This parameter likely influences the overall power or the initial number of spells the wand can hold.
*   **Structural Parameter:** `4` - This could relate to the number of spell slots, the complexity of the spell arrangement, or a similar structural attribute.
*   **Feature Flag:** `false` - This boolean parameter likely controls a specific feature or behavior during generation. Its exact effect is determined by the `gun_procedural_better.lua` script.

## Dependencies

This script relies on the following external file for its generation logic:

*   `data/scripts/gun/procedural/gun_procedural_better.lua`

This dependency means that the specific implementation and available options for wand generation are defined within that shared script.