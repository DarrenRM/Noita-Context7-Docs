---
title: Maggot Tiny Shot Behavior
category: entities
---

---

# Maggot Tiny Shot Behavior

This document describes the behavior of the `shot.lua` script associated with the "Maggot Tiny" entity in Noita. This script controls how the tiny maggot entity shoots projectiles.

## Core Functionality

The script primarily handles the firing of projectiles based on a counter stored within a `VariableStorageComponent`. It iterates through child entities, identifying them by their `GenomeDataComponent`, and fires a projectile from the child that corresponds to the current counter value.

## Key Attributes and Logic

*   **`entity_id`**: The unique identifier for the current entity.
*   **`x`, `y`**: The position of the entity.
*   **`vcomp`**: Stores the `VariableStorageComponent` that holds the shooting counter.
*   **`current`**: An integer representing the current stage of the shooting cycle. This determines which child entity will be used as the projectile origin.
*   **`VariableStorageComponent`**:
    *   **`name`**: Expected to be `"shooter_part"`.
    *   **`value_int`**: Stores the `current` shooting stage.
*   **Child Entity Iteration**:
    *   The script retrieves all child entities of the maggot.
    *   It checks each child for a `GenomeDataComponent`.
    *   A counter `i_` tracks the number of children with `GenomeDataComponent`.
*   **Projectile Firing**:
    *   When `i_` matches the `current` shooting stage, a projectile is fired.
    *   **`shoot_projectile` function**:
        *   `entity_id`: The ID of the entity firing the projectile.
        *   `"data/entities/animals/maggot_tiny/orb.xml"`: The projectile entity to be spawned.
        *   `px`, `py`: The position of the projectile's origin (taken from the child entity's transform).
        *   `0`, `0`: Initial velocity components (x, y).
*   **Shooting Cycle Management**:
    *   The `current` value is incremented after each shot.
    *   If `current` exceeds `33`, it resets to `1`, creating a cyclical shooting pattern.
    *   The `value_int` in the `VariableStorageComponent` is updated with the new `current` value.

## Summary of Logic Flow

1.  Get the entity's ID and transform.
2.  Locate the `VariableStorageComponent` named `"shooter_part"`.
3.  Retrieve the current shooting stage (`current`) from the component.
4.  If `current` is valid and the component is found:
    *   Iterate through child entities.
    *   Identify children with `GenomeDataComponent`.
    *   If the child's index in this sequence matches `current`:
        *   Get the child's position.
        *   Fire a projectile (`orb.xml`) from that position.
    *   Increment `current`.
    *   Reset `current` to `1` if it exceeds `33`.
    *   Update the `current` value in the `VariableStorageComponent`.