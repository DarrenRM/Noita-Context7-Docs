---
title: Wand Always Cast Action
category: scripts
---

---

# Wand Always Cast Action

This script adds a permanent "always cast" action to a wand. When a wand with this component is equipped, it will continuously cast the spell specified in the `value_string` of the `always_cast_action` component.

## Key Components

### `always_cast_action` Component

This is the primary component that defines the spell to be always cast.

*   **`value_string`**: A string representing the spell ID to be continuously cast.

## Usage

This script is intended to be attached to a wand entity. The `always_cast_action` component should be added to the wand, with its `value_string` set to the desired spell ID.

### Example Configuration (Conceptual)

```lua
-- This is a conceptual example of how the component might be added to a wand.
-- The actual implementation would be within the wand's entity definition.

{
    id = "my_always_cast_wand",
    components = {
        -- ... other wand components ...
        {
            id = "always_cast_action",
            value_string = "SPELL_ID_TO_ALWAYS_CAST" -- e.g., "data/scripts/magic/magic_missile.lua"
        }
    }
}
```

## Script Logic

1.  **Retrieve Entity ID**: Gets the ID of the entity the script is attached to.
2.  **Check for Component**: Looks for a variable storage component named `always_cast_action`.
3.  **Add Permanent Action**: If the component exists, it retrieves the `value_string` (the spell ID) and adds it as a permanent gun action to the wand using `AddGunActionPermanent`.