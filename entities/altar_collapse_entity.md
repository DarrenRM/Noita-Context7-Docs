---
title: Altar Collapse Entity
category: entities
---

# Altar Collapse Entity

This document describes the `altar_collapse` entity in Noita, which is a special type of altar that triggers a collapse effect.

## Entity Definition

The core definition of the `altar_collapse` entity is as follows:

```xml
<Entity name="altar_collapse" tags="altar_collapse" />
```

### Key Attributes:

*   **`name`**: `altar_collapse` - The unique identifier for this entity.
*   **`tags`**: `altar_collapse` - A tag used for internal referencing and potentially for game logic to identify this specific type of altar.

## Functionality

The `altar_collapse` entity is designed to initiate a collapse event within the game. While the provided XML is minimal, this entity likely serves as a trigger or a marker for a more complex system that handles the visual and physical effects of an altar collapsing.

### Potential Associated Components (Not present in this minimal XML):

Based on typical Noita entity structures, an `altar_collapse` entity would likely be accompanied by other components to define its behavior, such as:

*   **`ActionComponent`**: To define what actions are triggered when the altar is interacted with or activated.
*   **`ParticleEmitterComponent`**: To spawn visual effects during the collapse.
*   **`DamageComponent`**: If the collapse itself can cause damage.
*   **`AreaEffectComponent`**: To apply effects to entities within a certain radius.
*   **`PhysicsComponent`**: To handle the physical aspects of the collapse, such as falling debris.

This minimal definition suggests that the primary logic for the collapse is handled elsewhere, possibly through scripts or other linked entities.