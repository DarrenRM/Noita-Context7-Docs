---
title: Boss Alchemist Projectile Counter Damage Logic
category: entities
---

---

# Boss Alchemist Projectile Counter Damage Logic

This script defines the damage reception logic for the Boss Alchemist's projectile counter. It tracks cumulative damage and triggers the creation of a projectile counter entity when certain damage thresholds are met.

## Core Functionality

The `damage_received` function is the primary handler for incoming damage.

### Key Attributes and Logic

*   **`damage_received( damage )`**: This function is called when the entity takes damage.
    *   It retrieves the entity's ID and initializes variables for cumulative damage and a component reference.
    *   It iterates through the `VariableStorageComponent` to find a variable named `"damage_received"`.
    *   If found, it updates the `value_float` of this variable by adding the incoming `damage`.
    *   **Damage Thresholds**:
        *   If the individual `damage` is greater than or equal to `2.0`, OR
        *   If the `cumulative` damage is greater than or equal to `3.0`,
        *   The script proceeds to spawn a projectile counter.
    *   **Projectile Counter Spawning**:
        *   The entity's transform (position) is retrieved.
        *   A new entity, `data/entities/animals/boss_alchemist/projectile_counter.xml`, is loaded at the entity's position.
        *   The newly spawned entity is added as a child to the current entity.
    *   **Damage Reset/Reduction**:
        *   If a `dcomp` (the damage\_received variable component) was found, its value is reduced by `3.0` to reflect the damage that triggered the counter.