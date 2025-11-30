---
title: Broken Spell Pickup
category: entities
---

# Broken Spell Pickup

This document details the `summon_portal_broken.xml` entity, representing a broken spell pickup item in Noita.

## Core Functionality

This entity functions as a pickup item that, when thrown, attempts to summon a portal. It has physics properties for interaction and visual components for display.

### Key Components:

*   **`PhysicsBodyComponent`**: Manages the physical properties of the item, including damping, sleep behavior, and collision.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation of the item in the game world using `broken_spell.png`.
*   **`PhysicsThrowableComponent`**: Enables the item to be thrown with specific force and torque parameters.
*   **`ItemComponent`**: Identifies the entity as an item, sets its name (`$action_broken_spell`), and defines its pick-up and equip behavior.
*   **`AbilityComponent`**: Grants the item the ability to be thrown as an item, with a `deck_capacity` of 0, indicating it doesn't hold spells.

## Visuals and Effects

The entity includes several components for visual feedback and particle effects.

### Key Visual Components:

*   **`SpriteComponent`**: Defines the sprite displayed when the item is held in hand.
*   **`LightComponent`**: Emits a subtle light effect around the item, with parameters for radius, color, and fading.
*   **`SpriteParticleEmitterComponent` (x2)**:
    *   One emitter uses `ray.xml` for a visual effect when the item is in the world, with parameters for color, velocity, scale, and emission patterns.
    *   Another emitter uses `spark_electric.xml` for electrical sparks, active both in the world and when held, with parameters for color, gravity, emission count, and randomization.
*   **`ParticleEmitterComponent`**: Emits `spark_electric` material particles when the item is in the world or held, with parameters for velocity, lifetime, and emission rate.

## Variables

The entity utilizes `VariableStorageComponent` to manage internal states.

### Key Variables:

*   **`spells_remaining`**: An integer variable, initialized to `0`.
*   **`throw_time`**: An integer variable, initialized to `0`.

## Summary of Key Attributes:

| Component Type              | Key Attributes / Values