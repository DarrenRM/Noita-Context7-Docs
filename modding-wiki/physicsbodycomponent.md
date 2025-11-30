---
title: PhysicsBodyComponent
source: https://noita.wiki.gg/wiki/Documentation:PhysicsBodyComponent
category: modding-wiki
---

# PhysicsBodyComponent

This documentation page details the `PhysicsBodyComponent` in Noita, a crucial component for defining how entities interact with the game's physics engine. Understanding and modifying this component is essential for modders looking to alter entity behavior, movement, collision, and physical properties.

## Overview

The `PhysicsBodyComponent` is responsible for all aspects of an entity's physical presence within the Noita world. This includes its mass, friction, collision shape, and how it responds to forces like gravity and impacts. By adjusting the parameters within this component, modders can create entities that are heavy and immovable, light and easily pushed, or possess unique collision properties.

## Component Properties

The `PhysicsBodyComponent` is defined within an entity's XML file and contains numerous properties that control its physical behavior.

### Core Properties

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `mass` | float | The mass of the physics body. Higher mass means it's harder to move. | 1.0 |
| `friction` | float | The friction applied to the physics body. Higher friction means it will slow down more when sliding. | 0.5 |
| `restitution` | float | The bounciness of the physics body. A value of 0 means no bounce, 1 means perfect bounce. | 0.2 |
| `linear_damping` | float | Damping applied to linear velocity. Reduces movement over time. | 0.0 |
| `angular_damping` | float | Damping applied to angular velocity. Reduces rotation over time. | 0.0 |
| `is_static` | bool | If true, the body will not move or be affected by physics forces. | false |
| `is_kinematic` | bool | If true, the body can be moved by script but will not be affected by physics forces. | false |
| `collision_material` | string | The material used for collision. Affects sound and particle effects on impact. | "default" |
| `collision_shape` | string | Defines the shape of the collision body. Common values include "box", "circle", "capsule". | "box" |
| `collision_radius` | float | Radius for circular or capsule collision shapes. | 0.0 |
| `collision_box_size` | vec2 | Width and height for box collision shapes. | (0,0) |
| `collision_offset` | vec2 | Offset for the collision shape relative to the entity's center. | (0,0) |
| `gravity_scale` | float | Multiplier for the effect of gravity on this body. | 1.0 |
| `enable_impact_damage` | bool | If true, the entity can deal damage on impact. | false |
| `impact_damage_min_force` | float | Minimum force required to trigger impact damage. | 0.0 |
| `impact_damage_multiplier` | float | Multiplier for damage dealt by impact. | 1.0 |
| `impact_damage_type` | string | The type of damage dealt by impact (e.g., "damage_melee", "damage_explosion"). | "damage_melee" |
| `impact_damage_effect_type` | string | The visual effect type for impact damage. | "damage_effect_normal" |
| `impact_damage_effect_radius` | float | Radius of the impact damage effect. | 0.0 |
| `impact_damage_effect_force` | float | Force of the impact damage effect. | 0.0 |
| `impact_damage_effect_sound` | string | Sound played when impact damage occurs. | "" |
| `impact_damage_effect_particle` | string | Particle effect played when impact damage occurs. | "" |

### Example XML

```xml
<PhysicsBodyComponent
    mass="2.0"
    friction="0.7"
    restitution="0.3"
    linear_damping="0.1"
    angular_damping="0.1"
    collision_material="wood"
    collision_shape="box"
    collision_box_size="1,1"
    gravity_scale="1.5"
    enable_impact_damage="true"
    impact_damage_min_force="10.0"
    impact_damage_multiplier="2.0"
    impact_damage_type="damage_crush"
    impact_damage_effect_sound="sounds/impact_heavy.wav"
/>
```

## Lua Scripting Interaction

The `PhysicsBodyComponent` can be accessed and manipulated via Lua scripting. This allows for dynamic changes to an entity's physics properties during gameplay.

### Accessing the Component

You can get a reference to the `PhysicsBodyComponent` of an entity using the `GetComponent` function:

```lua
local entity = GetEntity("my_entity_id")
local physics_component = entity.GetComponent("PhysicsBodyComponent")

if physics_component then
    -- Interact with the physics_component
end
```

### Modifying Properties

Once you have a reference to the `PhysicsBodyComponent`, you can modify its properties:

```lua
if physics_component then
    physics_component.mass = 5.0
    physics_component.friction = 1.0
    physics_component.is_static = true
end
```

### Applying Forces

You can also apply forces to the physics body to move it:

```lua
if physics_component then
    -- Apply a force in the X direction
    physics_component.AddForce(100, 0)

    -- Apply an impulse (instantaneous force)
    physics_component.AddImpulse(0, 50)

    -- Apply torque (rotational force)
    physics_component.AddTorque(20)
end
```

### Useful Lua Functions

*   `entity.GetComponent("PhysicsBodyComponent")`: Retrieves the `PhysicsBodyComponent` of an entity.
*   `physics_component.AddForce(x, y)`: Applies a continuous force to the physics body.
*   `physics_component.AddImpulse(x, y)`: Applies an instantaneous impulse to the physics body.
*   `physics_component.AddTorque(torque)`: Applies a rotational force.
*   `physics_component.GetVelocity()`: Returns the current linear velocity of the physics body as a `vec2`.
*   `physics_component.GetAngularVelocity()`: Returns the current angular velocity of the physics body.
*   `physics_component.SetVelocity(x, y)`: Sets the linear velocity of the physics body.
*   `physics_component.SetAngularVelocity(velocity)`: Sets the angular velocity of the physics body.

## Collision Materials

The `collision_material` property determines the physical properties of collisions, influencing sounds, particle effects, and how entities interact.

### Common Collision Materials

| Material Name | Description |
|---|---|
| `default` | The standard collision material. |
| `wood` | Used for wooden objects, often with a duller impact sound. |
| `stone` | Used for stone objects, typically with a harder impact sound. |
| `metal` | Used for metallic objects, often with a sharp, ringing impact sound. |
| `organic` | Used for organic materials, may produce squishier sounds. |
| `liquid` | Used for interactions with liquids. |
| `ice` | Used for ice, often with reduced friction and a slippery feel. |
| `glass` | Used for glass, may shatter on impact. |

Modders can define their own custom collision materials in their mod's configuration files.

## Collision Shapes

The `collision_shape` property defines the geometric representation of an entity for physics calculations.

### Supported Collision Shapes

*   `box`: A rectangular collision shape. Requires `collision_box_size`.
*   `circle`: A circular collision shape. Requires `collision_radius`.
*   `capsule`: A capsule shape, which is a rectangle with rounded ends. Requires `collision_radius` and `collision_box_size` (for the rectangular portion).

The `collision_radius` and `collision_box_size` properties are used in conjunction with the `collision_shape` to define the exact dimensions of the collision body. The `collision_offset` can be used to position the collision shape relative to the entity's origin.

## Further Reading

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity XML Structure](https://noita.wiki.gg/wiki/Modding:_Entity_XML_Structure)