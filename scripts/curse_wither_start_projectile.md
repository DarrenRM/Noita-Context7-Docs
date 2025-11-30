---
title: Curse Wither Start Projectile
category: scripts
---

---

# Curse Wither Start Projectile

This script defines the behavior for a projectile that applies a "wither" curse effect, specifically by increasing damage multipliers for a certain curse type.

## Key Functionality

The primary purpose of this script is to modify the `DamageModelComponent` of the root entity (likely the player or an enemy) to increase the damage multiplier associated with a specific curse type.

### Core Attributes & Logic

*   **`entity_id`**: The unique identifier for the projectile entity.
*   **`root_id`**: The unique identifier for the root entity associated with the projectile (e.g., the caster).
*   **`VariableStorageComponent`**: Used to retrieve the `effect_curse_wither_type` which specifies the curse to be affected.
*   **`DamageModelComponent`**: The component on the root entity that stores damage multipliers.
*   **`damage_multipliers`**: A table within `DamageModelComponent` where specific curse types have their damage multipliers defined.

### Workflow

1.  The script identifies the projectile's entity and its root entity.
2.  It reads the `effect_curse_wither_type` from the projectile's `VariableStorageComponent`. This string determines which curse's damage multiplier will be affected.
3.  It accesses the `DamageModelComponent` of the root entity.
4.  It retrieves the current damage multiplier for the specified curse type from the `damage_multipliers` table.
5.  It increases this multiplier by `0.25`.
6.  The updated multiplier is then set back into the `damage_multipliers` table.

### Example Usage (Conceptual)

If the `effect_curse_wither_type` is "curse\_fire", and the player has a `damage_multipliers` entry like `curse_fire = 0.5`, after this script runs, it will become `curse_fire = 0.75`.