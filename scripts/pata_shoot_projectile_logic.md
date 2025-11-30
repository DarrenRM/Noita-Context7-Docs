---
title: Pata Shoot Projectile Logic
category: scripts
---

---

# Pata Shoot Projectile Logic

This script defines the behavior for a "Pata" entity when it shoots a projectile. It calculates projectile velocity, applies forces and torque to the entity, and manages a shooting timer to control its active state.

## Key Functions and Logic

### Projectile Firing

*   **`shoot_projectile(...)`**: This core function is called to spawn a projectile.
    *   **Projectile Type**: The projectile spawned is dynamically determined by `pata_rocket_` followed by a random number from 1 to 6, indicating different rocket variations.
    *   **Spawn Position**: The projectile is spawned slightly ahead of the entity's current position, based on its calculated velocity.
    *   **Velocity**: The projectile's velocity is calculated based on a random rotation (`r_`) and a base speed of 100.

### Entity Physics Manipulation

*   **`PhysicsApplyForce(entity_id, fx, fy)`**: Applies a random force to the entity.
    *   `fx`, `fy`: Random values between -240 and 240 are used for the X and Y components of the force.
*   **`PhysicsApplyTorque(entity_id, ft)`**: Applies a random rotational force (torque) to the entity.
    *   `ft`: A random value between -240 and 240 is used for the torque.

### Shooting Timer and State Management

*   **`VariableStorageComponent`**: The script interacts with a `VariableStorageComponent` tagged with `"pata_times_shot"` to track how many times the entity has shot.
    *   **`timer`**: An integer value stored in the component, incremented with each shot.
    *   **State Transition**: When `timer` exceeds 20:
        *   The entity's components tagged with `"pata_active"` are disabled.
        *   The entity's components tagged with `"pata_inactive"` are enabled.
        *   The `timer` is reset to 0.
    *   **Timer Update**: The `timer` value is updated in the `VariableStorageComponent` after each shot.

## Key Attributes/Elements

| Attribute/Element        | Description