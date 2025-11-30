---
title: Scavenger Mine Entity
category: entities
---

# Scavenger Mine Entity

This document describes the `scavenger_mine.xml` entity, a type of enemy found in Noita.

## Base Entity

The `scavenger_mine.xml` inherits its base properties from `data/entities/animals/scavenger_mine.xml`. The `include_children="1"` attribute indicates that it also incorporates child entities.

## Damage Component

The `DamageModelComponent` defines the combat attributes of the Scavenger Mine.

### Key Attributes:

*   **hp**: The current health points of the entity.
    *   Value: `7`
*   **max_hp**: The maximum health points the entity can have.
    *   Value: `7`
*   **minimum_knockback_force**: The minimum force required to knock back this entity. This is set very high, suggesting it's resistant to being pushed.
    *   Value: `100000`