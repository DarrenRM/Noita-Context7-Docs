---
title: Gate Monster Death Behavior
category: entities
---

# Gate Monster Death Behavior

This script defines the behavior that occurs when a "Gate Monster" entity in Noita dies. It handles item drops, sets game flags, and checks for the overall defeat of all gate monsters.

## Key Functions

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called automatically when the entity it's attached to is destroyed.

*   **`damage_type_bit_field`**: A bitmask representing the type of damage that killed the entity.
*   **`damage_message`**: A string describing the damage.
*   **`entity_thats_responsible`**: The ID of the entity that dealt the killing blow.
*   **`drop_items`**: A boolean indicating whether items should be dropped.

## Core Logic

### Entity Identification and Seed Generation

1.  **Get Entity ID and Position**: Retrieves the unique ID and world coordinates of the dying entity.
2.  **Determine Monster Type**: Checks the entity's name to identify which specific Gate Monster it is (e.g., `$animal_gate_monster_b`, `$animal_gate_monster_c`, etc.). This determines a `seed_offset`.
3.  **Set Random Seed**: Uses the `seed_offset` and the entity's horizontal position (`pw`) to generate a unique random seed. This ensures consistent random outcomes for item drops based on the monster and its location.

### Item Dropping

*   **`make_random_card(pos_x, pos_y)`**: This function is called to generate a random item drop at the monster's location. The specific item dropped is determined by the random seed set in the previous step.

### Flag Management

1.  **Set Individual Kill Flag**:
    *   `GameAddFlagRun(EntityGetName(entity_id) .. "_killed")`
    *   This line sets a temporary game flag that marks the specific monster as killed. For example, if `$animal_gate_monster_b` is killed, the flag `$animal_gate_monster_b_killed` will be set.

2.  **Check for All Gate Monsters Defeated**:
    *   The script checks if all four primary Gate Monsters (`$animal_gate_monster_a`, `b`, `c`, `d`) have been killed by verifying the presence of their respective `_killed` flags.
    *   **`AddFlagPersistent( "miniboss_gate_monsters" )`**: If all four monsters are confirmed dead, a persistent game flag named `"miniboss_gate_monsters"` is added. This flag likely signifies a major progression point in the game, potentially unlocking new areas or events.