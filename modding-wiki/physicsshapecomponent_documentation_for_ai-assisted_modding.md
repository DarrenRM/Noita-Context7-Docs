---
title: PhysicsShapeComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:PhysicsShapeComponent
category: modding-wiki
---

# PhysicsShapeComponent Documentation

This document details the `PhysicsShapeComponent` in Noita, a crucial component for defining the physical collision shapes of entities. Understanding and manipulating this component is essential for modders looking to create custom entities, alter existing ones, or implement unique physical interactions within the game.

## Overview of PhysicsShapeComponent

The `PhysicsShapeComponent` is responsible for defining the geometric shape that the game's physics engine uses to detect collisions for an entity. This includes its size, type (e.g., circle, box, polygon), and how it interacts with the environment and other entities. Modifying this component allows for fine-grained control over how objects behave physically.

## Component Properties

The `PhysicsShapeComponent` has several properties that can be configured within an entity's XML definition.

### `shape_type`

Determines the type of collision shape used.

| Value      | Description                                     |
| :--------- | :---------------------------------------------- |
| `circle`   | A circular collision shape.                     |
| `box`      | A rectangular collision shape.                  |
| `polygon`  | A custom polygon defined by vertices.           |
| `capsule`  | A capsule shape, useful for elongated objects.  |
| `chain`    | A series of connected line segments.            |
| `edge`     | A single line segment.                          |
| `path`     | A complex path defined by a series of points.   |
| `spline`   | A smooth curve defined by control points.       |

### `radius`

Used for `circle` and `capsule` shape types. Defines the radius of the circle or the radius of the capsule's ends.

### `box_size`

Used for `box` shape types. Defines the width and height of the rectangular box.

### `friction`

Controls the amount of friction applied to the entity. Higher values mean more friction.

### `restitution`

Controls the bounciness of the entity. A value of 0 means no bounce, while higher values increase bounciness.

### `density`

Determines the mass of the entity based on its shape and size. Higher density means more mass.

### `collision_group`

Specifies which collision groups the entity belongs to. This affects which other entities it can collide with.

### `collision_mask`

Specifies which collision groups the entity *will* collide with.

### `is_collidable`

A boolean value ( `true` or `false`) that determines if the entity can participate in physics collisions.

### `is_static`

A boolean value ( `true` or `false`) that determines if the entity is considered static and will not be affected by physics forces.

### `is_kinematic`

A boolean value ( `true` or `false`) that determines if the entity is controlled by animation or script rather than physics simulation.

### `material`

Defines the physical material properties of the entity, affecting sound, friction, and other interactions.

## Example XML Definitions

Here are examples of how to define `PhysicsShapeComponent` for different entity types.

### Circle Shape Example

```xml
<PhysicsShapeComponent
    shape_type="circle"
    radius="5"
    friction="0.3"
    restitution="0.2"
    density="1.0"
    collision_group="enemy"
    collision_mask="player,environment"
    is_collidable="true"
    is_static="false"
    is_kinematic="false"
    material="wood"
/>
```

### Box Shape Example

```xml
<PhysicsShapeComponent
    shape_type="box"
    box_size="10,20"
    friction="0.5"
    restitution="0.1"
    density="2.0"
    collision_group="item"
    collision_mask="player,enemy,environment"
    is_collidable="true"
    is_static="false"
    is_kinematic="false"
    material="stone"
/>
```

### Polygon Shape Example

For polygon shapes, you define the vertices relative to the entity's origin.

```xml
<PhysicsShapeComponent
    shape_type="polygon"
    vertices="0,0 10,0 10,10 0,10"
    friction="0.4"
    restitution="0.3"
    density="1.5"
    collision_group="hazard"
    collision_mask="player,environment"
    is_collidable="true"
    is_static="false"
    is_kinematic="false"
    material="metal"
/>
```

## Collision Groups and Masks

Understanding collision groups and masks is vital for controlling how entities interact.

### Default Collision Groups

| Group Name   | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `player`     | The player character.                                                    |
| `enemy`      | Enemies and hostile creatures.                                           |
| `item`       | Collectible items and projectiles.                                       |
| `environment`| Static world elements like walls, floors, and terrain.                   |
| `particle`   | Small visual effects and particles.                                      |
| `all`        | A special group that collides with everything.                           |
| `none`       | A special group that collides with nothing.                              |

### How Masks and Groups Work

*   An entity with `collision_group="A"` and `collision_mask="B,C"` will collide with entities that have `collision_group` set to `B` or `C`.
*   An entity with `collision_group="B"` and `collision_mask="A"` will collide with entities that have `collision_group` set to `A`.
*   For a collision to occur, both entities must have their respective groups and masks set up to allow it.

## Lua API for PhysicsShapeComponent

While most physics shape properties are defined in XML, some aspects can be influenced or queried via Lua scripting.

### Accessing PhysicsShapeComponent in Lua

You can access the `PhysicsShapeComponent` of an entity using its entity ID.

```lua
local entity_id = GetPlayer() -- Example: Get the player entity ID
local physics_component = EntityGetFirstComponent(entity_id, "PhysicsShapeComponent")

if physics_component then
    -- You can now interact with the component
    -- Note: Direct modification of shape properties via Lua might be limited or require specific functions.
    -- For example, you might be able to get its current state or trigger physics events.
end
```

### Useful Lua Functions (Related to Physics)

*   `EntityGetFirstComponent(entity_id, component_name)`: Retrieves the first instance of a specified component from an entity.
*   `EntityGetLimboState(entity_id)`: Checks if an entity is in limbo (e.g., not actively simulated).
*   `PhysicsObjectApplyForce(entity_id, force_x, force_y)`: Applies a force to the physics object of an entity.
*   `PhysicsObjectAddVelocity(entity_id, velocity_x, velocity_y)`: Adds velocity to the physics object.

For more detailed information on Lua scripting and available functions, refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).

## Important Considerations for Modding

*   **Performance:** Complex polygon shapes or a very large number of entities with physics can impact game performance. Optimize shapes where possible.
*   **Entity Origin:** Be mindful of the entity's origin point when defining shapes, especially polygons.
*   **Testing:** Thoroughly test your custom entities and their physics interactions to ensure they behave as intended.
*   **Compatibility:** Ensure your physics configurations do not conflict with other mods if you are creating content for a modded environment.

This documentation provides a foundational understanding of the `PhysicsShapeComponent`. For advanced use cases and specific interactions, further experimentation and consultation of the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) are recommended.