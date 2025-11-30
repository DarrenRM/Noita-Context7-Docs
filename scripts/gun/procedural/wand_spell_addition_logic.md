---
title: Wand Spell Addition Logic
category: scripts/gun/procedural
---

# Wand Spell Addition Logic

This script defines how spells are added to wands, specifically focusing on the "always cast" functionality. It leverages utility functions to access and apply spell data to entities.

## Core Functionality

The primary purpose of this script is to read a spell identifier from a variable storage component attached to a wand entity and then add that spell to the wand's action list. This is commonly used for implementing "always cast" effects on wands.

### Key Components and Actions

*   **`dofile("data/scripts/lib/utilities.lua")`**: Imports utility functions for general game logic.
*   **`dofile("data/scripts/gun/procedural/gun_action_utils.lua")`**: Imports functions specifically for managing gun actions.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity being processed (likely the wand).
*   **`get_variable_storage_component(entity_id, "extra_spell")`**: Attempts to find a component on the entity that stores a variable named "extra_spell". This component is expected to hold the spell to be added.
*   **`ComponentGetValue(comp, "value_string")`**: If the "extra_spell" component is found, this function extracts its string value, which is assumed to be the name of the spell.
*   **`AddGunAction(entity_id, spell_name)`**: Adds the extracted `spell_name` as an action to the specified `entity_id` (the wand).

## Usage Example (Conceptual)

Imagine a wand entity with a `VariableStorageComponent` attached. This component has a `value_string` set to `"fireball"`. When this script runs on that wand, it will effectively add the "fireball" spell to the wand's repertoire, making it cast automatically.

```lua
-- Example of how a wand might be configured to use this script
-- (This is illustrative and not part of the provided script itself)

local wand_entity = create_wand_entity() -- Assume this function exists
local spell_to_add = "lightning_bolt"

-- Add a component to the wand to store the spell name
local storage_comp = wand_entity:add_component(VariableStorageComponent())
storage_comp:set_value_string("extra_spell", spell_to_add)

-- Then, this script would be executed on wand_entity
-- to add "lightning_bolt" as an always cast spell.
```