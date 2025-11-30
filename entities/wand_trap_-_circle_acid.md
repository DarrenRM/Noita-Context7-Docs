---
title: Wand Trap - Circle Acid
category: entities
---

# Wand Trap - Circle Acid

This entity defines a wand trap that, when triggered, spawns a "circle_acid" projectile.

## Key Components

*   **`wand_trap` tag**: Identifies this entity as a wand trap.
*   **`VariableStorageComponent`**:
    *   `name="entity_file"`: Specifies the file path to the entity that will be spawned.
    *   `value_string="data/entities/projectiles/deck/circle_acid.xml"`: This is the crucial part, indicating that the `circle_acid.xml` projectile will be created.

## Functionality

When a wand trap with this configuration is activated (e.g., by a player interacting with it or a specific game event), it will instantiate the entity defined by `data/entities/projectiles/deck/circle_acid.xml`. This typically means it will fire a projectile with acid properties.