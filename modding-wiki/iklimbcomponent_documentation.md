---
title: IKLimbComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:IKLimbComponent
category: modding-wiki
---

# IKLimbComponent Documentation

This documentation covers the `IKLimbComponent` in Noita, a crucial component for defining and controlling the Inverse Kinematics (IK) behavior of character limbs. Understanding this component is essential for modders looking to create custom animations, character behaviors, or modify existing ones that rely on IK for realistic limb posing.

## Overview of IKLimbComponent

The `IKLimbComponent` is responsible for managing the Inverse Kinematics system for a specific limb. IK allows for more natural and dynamic limb movement by calculating the joint angles required to reach a target position. This is particularly useful for characters interacting with the environment, such as reaching for ledges, gripping objects, or adjusting their stance.

## Component Properties

The `IKLimbComponent` has several properties that can be configured in your mod's XML files to customize its behavior.

### Core Properties

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `limb_length` | float | The total length of the limb. | N/A |
| `segment_count` | int | The number of segments the limb is divided into for IK calculations. Higher values allow for more complex curves. | N/A |
| `segment_length` | float | The length of each individual segment. This is often derived from `limb_length` and `segment_count`. | N/A |
| `joint_stiffness` | float | Controls how much the joints resist bending. Higher values make the limb more rigid. | N/A |
| `joint_damping` | float | Controls how quickly joint movement dissipates. Helps prevent oscillations. | N/A |
| `target_reach_distance` | float | The maximum distance the limb can reach towards its target. | N/A |
| `target_reach_stiffness` | float | How strongly the limb tries to reach the target. | N/A |
| `target_reach_damping` | float | How quickly the limb settles when reaching the target. | N/A |
| `pole_vector_influence` | float | Controls the influence of the pole vector, which helps define the general direction of the limb. | N/A |
| `pole_vector_stiffness` | float | How strongly the limb adheres to the pole vector. | N/A |
| `pole_vector_damping` | float | How quickly the limb settles when aligning with the pole vector. | N/A |
| `enable_ik` | bool | Whether IK is enabled for this limb. | N/A |

### Example XML Configuration

```xml
<IKLimbComponent
    limb_length="1.5"
    segment_count="3"
    joint_stiffness="10.0"
    joint_damping="2.0"
    target_reach_distance="2.0"
    target_reach_stiffness="5.0"
    target_reach_damping="1.0"
    pole_vector_influence="0.5"
    pole_vector_stiffness="3.0"
    pole_vector_damping="0.5"
    enable_ik="true"
/>
```

## Usage in Mods

The `IKLimbComponent` is typically added to entities in Noita's XML files. You would define an entity and then attach this component to it, configuring its properties as needed.

### Attaching to an Entity

```xml
<Entity name="my_custom_character">
    <IKLimbComponent
        limb_length="1.0"
        segment_count="2"
        enable_ik="true"
        // ... other properties
    />
    <!-- Other components for the entity -->
</Entity>
```

### Controlling IK Targets via Lua

The IK target for a limb can often be controlled dynamically using Lua scripting. This allows for interactive and responsive character animations. You would typically get a reference to the entity and then access its `IKLimbComponent` to set the target position.

```lua
-- Assuming 'entity' is a reference to an entity with an IKLimbComponent
local ik_limb_component = entity:GetComponent("IKLimbComponent")

if ik_limb_component then
    -- Set the IK target position (e.g., to a specific world coordinate)
    local target_position = Vector3(10.0, 5.0, 0.0)
    ik_limb_component:SetTargetPosition(target_position)

    -- You can also set the pole vector if needed
    local pole_vector = Vector3(0.0, 1.0, 0.0)
    ik_limb_component:SetPoleVector(pole_vector)
end
```

## Related Components and Concepts

*   **`TransformComponent`**: Provides the spatial transformation (position, rotation, scale) for an entity, which is fundamental for IK calculations.
*   **`AnimationComponent`**: While IK can drive limb posing, it often works in conjunction with or overrides parts of the animation system.
*   **Inverse Kinematics (IK)**: The mathematical process of calculating joint parameters that result in a desired end-effector position and orientation.

## Further Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity XML Structure](https://noita.wiki.gg/wiki/Modding:_Entity_XML_Structure)