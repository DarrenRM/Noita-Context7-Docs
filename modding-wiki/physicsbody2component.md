---
title: PhysicsBody2Component
source: https://noita.wiki.gg/wiki/Documentation:PhysicsBody2Component
category: modding-wiki
---

# PhysicsBody2Component

This documentation page details the `PhysicsBody2Component` in Noita, a crucial component for defining the physical properties of entities. Understanding and modifying this component is essential for AI-assisted modding, allowing for fine-grained control over how objects interact with the game's physics engine, affecting movement, collision, and overall behavior.

## Overview

The `PhysicsBody2Component` is responsible for defining an entity's physical characteristics within Noita's 2D physics simulation. This includes properties like mass, friction, restitution (bounciness), and how it interacts with forces and collisions. Modifying these values can drastically alter how an entity behaves, from making it heavy and immovable to light and easily propelled.

## Component Properties

The `PhysicsBody2Component` has several properties that can be adjusted in your modding projects. These properties are typically defined within an entity's XML definition file.

### `mass`

*   **Type:** `float`
*   **Description:** The mass of the physics body. Higher mass means it's harder to move and it will exert more force when moving.
*   **Default Value:** `1.0`

### `friction`

*   **Type:** `float`
*   **Description:** The coefficient of friction. This determines how much an object resists sliding against other surfaces. A value of 0 means no friction, while higher values increase resistance.
*   **Default Value:** `0.5`

### `restitution`

*   **Type:** `float`
*   **Description:** The coefficient of restitution, often referred to as bounciness. A value of 0 means no bounce, while a value of 1 means a perfectly elastic collision (no energy loss).
*   **Default Value:** `0.2`

### `linear_damping`

*   **Type:** `float`
*   **Description:** Linear damping reduces the velocity of the physics body over time, simulating air resistance or other forms of drag. A value of 0 means no damping.
*   **Default Value:** `0.0`

### `angular_damping`

*   **Type:** `float`
*   **Description:** Angular damping reduces the rotational velocity of the physics body over time. A value of 0 means no damping.
*   **Default Value:** `0.0`

### `is_static`

*   **Type:** `bool`
*   **Description:** If `true`, the physics body will not move or be affected by physics forces. It essentially becomes a fixed part of the environment.
*   **Default Value:** `false`

### `is_kinematic`

*   **Type:** `bool`
*   **Description:** If `true`, the physics body can be moved by script but will not be affected by physics forces (like gravity or collisions). It will still affect other physics bodies.
*   **Default Value:** `false`

### `collision_material`

*   **Type:** `string`
*   **Description:** Specifies the collision material for the physics body. This can affect how it interacts with other physics bodies and the sounds/effects produced during collisions. Common values include "default", "wood", "metal", "flesh", etc.
*   **Default Value:** `default`

### `physics_type`

*   **Type:** `enum`
*   **Description:** Defines the type of physics simulation to use for this body.
*   **Possible Values:**
    *   `dynamic`: The body is fully simulated by the physics engine.
    *   `static`: The body is fixed in place and does not move.
    *   `kinematic`: The body can be moved by script but is not affected by physics forces.

### `enable_impact_damage`

*   **Type:** `bool`
*   **Description:** If `true`, the entity can deal damage to other entities based on its impact velocity.
*   **Default Value:** `false`

### `impact_damage_multiplier`

*   **Type:** `float`
*   **Description:** A multiplier for the damage dealt by impact. Only relevant if `enable_impact_damage` is `true`.
*   **Default Value:** `1.0`

## Example XML Implementation

Here's an example of how you might define a `PhysicsBody2Component` for an entity in an XML file:

```xml
<Entity name="my_heavy_object">
    <PhysicsBody2Component mass="10.0" friction="0.8" restitution="0.1" linear_damping="0.1" collision_material="metal" enable_impact_damage="true" impact_damage_multiplier="2.0"/>
    <!-- Other components -->
</Entity>
```

This example creates an entity named "my\_heavy\_object" with a high mass, significant friction, low bounciness, some linear damping, a metal collision material, and the ability to deal impact damage.

## Modding Considerations

When using AI to assist with modding, you can leverage the understanding of `PhysicsBody2Component` to:

*   **Generate Entity Definitions:** Prompt the AI to create XML definitions for entities with specific physical properties (e.g., "create an entity that is very bouncy and light").
*   **Modify Existing Entities:** Provide the AI with an existing entity's XML and ask it to adjust its physics properties for a desired effect (e.g., "make this projectile explode on impact by increasing its restitution and enabling impact damage").
*   **Debug Physics Issues:** If an entity is behaving unexpectedly, the AI can help analyze its `PhysicsBody2Component` settings and suggest adjustments.
*   **Create Physics-Based Puzzles:** Design scenarios where entities with specific physics properties are required to solve a puzzle.

By understanding the parameters of `PhysicsBody2Component`, you can guide AI tools to generate more accurate and effective modding content, leading to more dynamic and engaging gameplay experiences in Noita.