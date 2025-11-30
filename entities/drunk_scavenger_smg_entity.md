---
title: Drunk Scavenger SMG Entity
category: entities
---

# Drunk Scavenger SMG Entity

This entity defines a "Drunk Scavenger" enemy in Noita, which is a variant of the standard Scavenger that is permanently under the effect of alcohol.

## Key Attributes

*   **`name`**: `$animal_scavenger_smg` - The internal identifier for this entity.
*   **`Base`**:
    *   `file="data/entities/animals/scavenger_smg.xml"`: Inherits all properties and behaviors from the base `scavenger_smg.xml` entity. This means it will have the same movement, attack patterns, and visual appearance as a regular Scavenger with an SMG.
    *   `include_children="1"`: Ensures that all child elements from the base file are included.

## Special Effects

*   **`Entity`**:
    *   **`Base`**:
        *   `file="data/entities/misc/effect_drunk_forever.xml"`: This is the core modification that makes this entity "drunk". It applies a permanent drunk effect to the entity.
        *   `include_children="1"`: Includes any child elements from the drunk effect definition.

## Summary

The `scavenger_smg.xml` entity is a straightforward modification of the base `scavenger_smg.xml` entity. It achieves its "drunk" state by inheriting from `effect_drunk_forever.xml`, which applies a persistent alcohol-induced effect. This means the entity will behave like a standard SMG-wielding scavenger but with the visual and potentially behavioral quirks associated with being drunk.