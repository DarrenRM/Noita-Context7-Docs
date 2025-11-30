---
title: Friend Status Modifiers
category: scripts
---

# Friend Status Modifiers

This script modifies the behavior and stats of an entity based on a "friend_status" variable stored in its `VariableStorageComponent`. The modifications are applied incrementally as the entity's "friend_status" count increases, up to a global "ULTIMATE_KILLER_KILLS" threshold.

## Core Logic

The script checks if the entity's current `friend_status` count is less than the global `ULTIMATE_KILLER_KILLS`. If it is, and the `friend_status` component exists, the following modifications are applied:

1.  **Stat Buffs:** The entity's `max_hp` and current `hp` are increased by 50%.
2.  **Damage Reduction:** Damage multipliers for "projectile" and "slice" types are reduced by 0.1.
3.  **Attack Speed:** The delay between ranged attacks (`attack_ranged_frames_between`) is reduced by 1 frame, with a minimum of 10 frames.
4.  **Immunities/Tags:** Specific immunities and tags are applied based on the iteration of the modification loop:
    *   **Iteration 0:** Grants "PROTECTION_MELEE", "BREATH_UNDERWATER" (infinite duration), and the "polymorphable_NOT" tag.
    *   **Iteration 1:** Grants "PROTECTION_FIRE", "PROTECTION_EXPLOSION" (infinite duration), and the "touchmagic_immunity" tag.
    *   **Iteration 2:** Grants "PROTECTION_FREEZE", "PROTECTION_ELECTRICITY" (infinite duration), and the "curse_NOT" tag.
5.  **Critical Hit Boost:** Grants "CRITICAL_HIT_BOOST" (infinite duration).
6.  **Health Bar Visibility:** The entity's health bar becomes visible.
7.  **Ranged Attack:** The entity's ranged attack projectile is set to `data/entities/projectiles/machinegun_bullet_roboguard_big.xml`.

Finally, the entity's `friend_status` count is updated to match the `ULTIMATE_KILLER_KILLS` threshold.

## Key Components and Variables

*   **`VariableStorageComponent`**: Stores custom variables for entities. The script specifically looks for a variable named "friend_status" with an integer value.
*   **`ULTIMATE_KILLER_KILLS`**: A global variable that defines the maximum threshold for applying friend status modifications.
*   **`DamageModelComponent`**: Contains damage-related properties like `max_hp`, `hp`, and `damage_multipliers`.
*   **`AnimalAIComponent`**: Manages the AI behavior of animal entities, including attack parameters.
*   **`SpriteComponent`**: Controls visual aspects of entities, including the visibility of the health bar.
*   **`Game Effect Components`**: Used to apply temporary or permanent effects to entities (e.g., protections, boosts).

## Example Usage (Conceptual)

This script is likely intended to be attached to an entity that can be "befriended" or influenced by the player's actions. As the player achieves certain milestones (represented by `ULTIMATE_KILLER_KILLS`), the entity gains power and new abilities.

```lua
-- Example of how a VariableStorageComponent might be set up for this script
-- This is not part of the script itself, but illustrates its dependency.

-- In an entity's .xml file:
-- <VariableStorageComponent
--     name="friend_status"
--     value_int="0" />
```