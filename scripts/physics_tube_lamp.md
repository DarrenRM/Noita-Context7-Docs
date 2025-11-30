---
title: Physics Tube Lamp
category: scripts
---

---

# Physics Tube Lamp

This script defines the behavior for a physics-based tube lamp entity in Noita. It handles visual effects like blinking and sparking, as well as physical interactions like breaking joints.

## Key Functionality

### `physics_body_modified( is_destroyed )`

This function is called when the physics body of the lamp is modified, typically when it's created or interacts with the environment.

*   **`entity_id`**: The unique identifier for the lamp entity.
*   **`x, y`**: The world coordinates of the lamp's transform.

### Visual Effects

*   **Blinking Light**: The lamp's light component is modified to blink at a frequency of `0.9`.
    ```lua
    edit_all_components( entity_id, "LightComponent", function(comp,vars)
        vars.blinking_freq = 0.9
    end)
    ```
*   **Sparking Effect**: The entity is tagged with `"electricity_effect"` to enable visual sparks.
    ```lua
    EntitySetComponentsWithTagEnabled( entity_id, "electricity_effect", true )
    ```

### Physical Interaction

*   **Broken Joint**: The script randomly selects one of the lamp's physics joints (identified by `joint_id`) and marks it for destruction. This simulates the lamp breaking apart.
    ```lua
    local broken_joint_id = ProceduralRandomi(x,y,1,2)
    edit_all_components2( entity_id, "PhysicsJoint2MutatorComponent", function(comp,vars)
        if ComponentGetValue2( comp, "joint_id" ) == broken_joint_id then
            vars.destroy = true
        end
    end)
    ```

## Components Targeted

This script interacts with the following component types:

*   `LightComponent`: Controls the visual light emitted by the lamp.
*   `PhysicsJoint2MutatorComponent`: Manages the physics joints connecting parts of the lamp.