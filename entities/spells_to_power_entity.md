---
title: Spells to Power Entity
category: entities
---

# Spells to Power Entity

This entity is a core component for the "Spells to Power" game mechanic in Noita. It utilizes Lua scripts to manage the logic for how spells are generated and potentially influence gameplay.

## Key Components

### LuaComponent (Primary Logic)

This component is responsible for executing the main "Spells to Power" logic.

*   **`script_source_file`**: `data/scripts/projectiles/spells_to_power.lua`
    *   This specifies the Lua script file that contains the primary logic for the "Spells to Power" system.
*   **`execute_every_n_frame`**: `1`
    *   Indicates that the script should execute every single frame, suggesting continuous or very frequent updates for this mechanic.
*   **`remove_after_executed`**: `1`
    *   This attribute is set to `1`, meaning the Lua component will be removed from the entity after its initial execution. This implies the core logic might be a one-time setup or trigger.

### LuaComponent (Tagging)

This component appears to be a helper or tagging mechanism for the "Spells to Power" system.

*   **`script_source_file`**: `data/scripts/projectiles/spells_to_power_tag.lua`
    *   This points to a Lua script likely used for tagging or marking entities related to the "Spells to Power" functionality.
*   **`execute_on_added`**: `1`
    *   The script will execute as soon as this component is added to the entity.
*   **`remove_after_executed`**: `1`
    *   Similar to the other component, this script will be removed after its execution, suggesting a one-time tagging action.

## Summary

The `spells_to_power.xml` entity defines a system that relies on two Lua scripts. One script (`spells_to_power.lua`) runs continuously to manage the core "Spells to Power" mechanics, while another (`spells_to_power_tag.lua`) is executed once upon entity creation to potentially tag or initialize related elements. The `remove_after_executed="1"` attribute on both components suggests that their primary function is to set up or trigger an event rather than to persist as active logic for the entity's entire lifespan.