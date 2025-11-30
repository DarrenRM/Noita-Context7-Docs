---
title: Drunk Miner (Weak) Entity
category: entities
---

# Drunk Miner (Weak) Entity

This document describes the `miner_weak.xml` entity, representing a weaker version of the drunk miner enemy in Noita.

## Entity Definition

The `miner_weak` entity inherits its core properties from `data/entities/animals/miner_weak.xml`. It also incorporates the `effect_drunk_forever.xml` entity, which applies a permanent drunk effect.

### Key Attributes

*   **`name`**: `$animal_miner` - The internal identifier for this entity.
*   **`Base file="data/entities/animals/miner_weak.xml"`**: Specifies the primary XML file defining the miner's base behavior and appearance.
*   **`include_children="1"`**: Indicates that all child elements from the base file should be included.
*   **`Entity`**: A nested entity definition.
    *   **`Base file="data/entities/misc/effect_drunk_forever.xml"`**: This crucial inclusion applies a permanent drunk status to the miner, affecting its behavior and potentially its movement or attack patterns.

## Summary

The `miner_weak.xml` entity defines a basic miner enemy that is permanently under the influence of alcohol. This drunk effect is achieved by including the `effect_drunk_forever.xml` entity. The entity inherits its fundamental characteristics from a separate `miner_weak.xml` file, suggesting a base template for weaker miners.