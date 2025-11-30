---
title: Curse Hit Effect
category: entities
---

# Curse Hit Effect

This entity defines a special hit effect that triggers the curse initialization sequence.

## Key Components

### HitEffectComponent

This component dictates what happens when the entity is hit.

*   **`effect_hit`**: Specifies the type of effect to apply.
    *   `LOAD_CHILD_ENTITY`: Indicates that a child entity should be loaded.
*   **`value_string`**: The path to the entity to be loaded as a child.
    *   `data/entities/misc/curse_init.xml`: This is the specific entity loaded, which handles the curse initialization logic.

## Usage

This entity is typically used as a component within other entities that should inflict a curse upon being hit. When an entity with this `HitEffectComponent` is struck, it will load and execute `curse_init.xml`, thereby applying the curse effect to the target.