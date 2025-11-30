---
title: Neutral Wizard Entity
category: entities
---

# Neutral Wizard Entity

This document describes the `wizard_neutral.xml` entity, a basic neutral wizard found in the game Noita. It focuses on key attributes relevant for AI-assisted modding.

## Core Entity Properties

The `wizard_neutral.xml` entity inherits from a base wizard entity and defines specific components to modify its behavior and appearance.

### Base Entity Inheritance

*   **`Base file="data/entities/animals/wizard_neutral.xml"`**: Indicates that this entity inherits properties from a base wizard definition.

### Damage Component

*   **`DamageModelComponent`**: Defines the wizard's health and resistance to knockback.
    *   `hp="14"`: The current health points of the wizard.
    *   `max_hp="14"`: The maximum health points of the wizard.
    *   `minimum_knockback_force="100000"`: A high value indicating significant resistance to being knocked back by attacks.

## Visual and Physics Components

This section details the visual elements and physics applied to the wizard.

### Cape Component

*   **`Entity name="cape"`**: Defines a cape as a distinct sub-entity.
    *   **`Base file="data/entities/verlet_chains/cape/cape.xml"`**: Inherits properties from a generic cape definition.
    *   **`VerletPhysicsComponent`**: Applies Verlet physics for cloth simulation.
        *   `cloth_color_edge="0xFF96acab"`: The color of the cape's edge (RGBA hex format).
        *   `cloth_color="0xFF4a4e5b"`: The main color of the cape (RGBA hex format).

### Status Effect Components

These entities grant the wizard immunity to certain status effects.

*   **`Entity`**: A generic entity container.
    *   **`InheritTransformComponent`**: Ensures the entity inherits the transform (position, rotation, scale) of its parent.
    *   **`GameEffectComponent`**: Applies a game effect.
        *   `effect="STUN_PROTECTION_FREEZE"`: Grants immunity to the freeze status effect.
        *   `frames="-1"`: Indicates the effect is permanent (lasts indefinitely).

*   **`Entity`**: Another generic entity container.
    *   **`InheritTransformComponent`**: Inherits transform.
    *   **`GameEffectComponent`**: Applies a game effect.
        *   `effect="STUN_PROTECTION_ELECTRICITY"`: Grants immunity to the electricity status effect.
        *   `frames="-1"`: Indicates the effect is permanent.