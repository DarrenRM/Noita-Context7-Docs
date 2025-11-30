---
title: Boss Meat Eye Entity
category: entities
---

---

# Boss Meat Eye Entity

This document describes the configuration and behavior of the "Boss Meat Eye" entity in Noita, focusing on its AI-driven modding aspects.

## Core Functionality

The Boss Meat Eye entity is a dynamic entity that cycles through different states, primarily controlled by a `VariableStorageComponent` acting as a status tracker. Its behavior involves visual animations, hitbox adjustments, and projectile spawning.

### Key Components and Attributes

*   **`SpriteComponent`**: Manages the visual representation of the eye.
*   **`VariableStorageComponent` (tag: "status")**:
    *   Stores an integer value representing the current state of the eye.
    *   This value dictates the entity's actions.
*   **`HitboxComponent`**:
    *   `damage_multiplier`: Controls the damage dealt by the eye. It's set to `1.0` when open and `0` when closed.

### State Machine and Behavior

The entity's behavior is driven by a simple state machine based on the `status` variable:

*   **Status 1 (Open)**:
    *   Triggers the "open" animation (`GamePlayAnimation`).
    *   Enables components tagged "vacuum".
    *   Disables components tagged "vacuum\_NOT".
    *   Sets `damage_multiplier` to `1.0`.
*   **Status 3 (Close/Shoot)**:
    *   Triggers the "close" animation (`GamePlayAnimation`).
    *   Disables components tagged "vacuum".
    *   Enables components tagged "vacuum\_NOT".
    *   Sets `damage_multiplier` to `0`.
    *   **Spawns a projectile**: `data/entities/animals/boss_meat/orb_big.xml` at the eye's current position.

### State Transition

After executing its actions for the current status, the `status` variable is incremented and then taken modulo 4 (`(status + 1) % 4`). This creates a cycle through states, likely 0, 1, 2, 3, and back to 0. The specific actions are tied to statuses 1 and 3.

### AI Modding Considerations

*   **State Manipulation**: Modders can directly alter the `value_int` of the "status" `VariableStorageComponent` to force the eye into specific states (e.g., open, closed, shooting).
*   **Animation Control**: The `GamePlayAnimation` function can be called with different animation names and parameters to customize the visual feedback.
*   **Hitbox and Damage**: Modifying the `damage_multiplier` of the `HitboxComponent` allows for adjustments to the eye's offensive capabilities.
*   **Projectile Spawning**: The `shoot_projectile` function can be used to spawn different projectile types or modify the parameters of the existing projectile.
*   **Component Tagging**: The use of tags like "vacuum" and "vacuum\_NOT" suggests a system for enabling/disabling related functionalities. Modders can leverage these tags or introduce their own for more complex interactions.