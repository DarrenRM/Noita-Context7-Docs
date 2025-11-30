---
title: Glue Death Projectile
category: scripts
---

---

# Glue Death Projectile

This script defines the behavior for a projectile that causes a "glue death" effect. When this projectile hits an entity, it triggers a visual explosion and potentially other effects defined by the `explosion_glue.xml` entity.

## Key Attributes

*   **`death` function:** This is the core function that is called when the projectile's death condition is met.
    *   It takes arguments for `damage_type_bit_field`, `damage_message`, `entity_thats_responsible`, and `drop_items`, though these are not explicitly used in this minimal example.
*   **`EntityLoad`:** This function is used to spawn a visual effect at the projectile's location.
    *   **`"data/entities/particles/particle_explosion/explosion_glue.xml"`:** Specifies the XML file defining the visual explosion particle effect.
    *   **`pos_x`, `pos_y`:** The coordinates where the explosion particle will be spawned, derived from the projectile's current position.

## Usage

This script is intended to be attached to a projectile entity. When that projectile collides with something and its death condition is met, this script will execute, creating a glue-themed explosion effect.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions, though none are explicitly called in this snippet.