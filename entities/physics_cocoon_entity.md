---
title: Physics Cocoon Entity
category: data/entities
---

# Physics Cocoon Entity

This document describes the `physics_cocoon.xml` entity, which represents a physics-based cocoon object in Noita. It's designed to be a destructible object that can contain and spill materials upon destruction.

## Key Attributes and Components

The `physics_cocoon.xml` entity is primarily defined by the following components:

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits core physics properties from the base physics item.

### Physics Components

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: Specifies the visual representation of the cocoon (`data/buildings_gfx/cocoon.png`).
    *   `material`: Defines the physics material for collision and interaction (`cocoon_box2d`).
*   **`PhysicsBodyComponent`**:
    *   `angular_damping`: Controls how quickly rotational motion decays (0.01).
    *   `linear_damping`: Controls how quickly linear motion decays (0.1).
*   **`PhysicsJointComponent`**:
    *   `nail_to_wall`: Indicates if the object is fixed to a wall (1, meaning yes).
    *   `pos_x`, `pos_y`: Relative position offset for the joint.

### Visual and Interaction Components

*   **`LightComponent`**:
    *   `radius`: The radius of the light emitted by the cocoon (100).
*   **`DamageModelComponent`**:
    *   `hp`: The health points of the cocoon (6).
    *   `critical_damage_resistance`: Resistance to critical damage (1, meaning full resistance).
    *   `fire_damage_amount`: Amount of fire damage it takes (0.2).
    *   `air_needed`: Whether air is required for its survival (0, meaning no).
*   **`ExplodeOnDamageComponent`**:
    *   `explode_on_death_percent`: Probability of exploding upon death (1.0, always explodes).
    *   `physics_body_destruction_required`: Threshold for physics body destruction to trigger explosion (0.4).
    *   **`config_explosion`**: Defines the properties of the explosion:
        *   `damage`: Damage dealt by the explosion (0).
        *   `camera_shake`: Intensity of camera shake (5).
        *   `explosion_radius`: Radius of the explosion (5).
        *   `explosion_sprite`: Visual effect for the explosion (`data/particles/explosion_008.xml`).
        *   `create_cell_probability`: Probability of creating material cells (10).
        *   `create_cell_material`: Material created upon explosion (`bone`).
        *   `physics_explosion_power.max`: Maximum physics force applied by the explosion (2).
        *   `stains_enabled`: Whether stains are created (1, yes).
        *   `stains_radius`: Radius of stains (10).

### Material Handling

*   **`MaterialInventoryComponent`**:
    *   `on_death_spill`: Whether materials spill on death (1, yes).
    *   `leak_on_damage_percent`: Percentage of damage at which materials leak (0.999).
    *   **`count_per_material_type`**: Defines the materials contained within the cocoon:
        *   `Material material="blood_worm" count="50"`: Contains 50 units of `blood_worm` material.

### Scripting

*   **`LuaComponent`**:
    *   `script_damage_received`: The Lua script executed when the entity receives damage (`data/scripts/buildings/worm_cocoon.lua`).
    *   `execute_every_n_frame`: How often the script is executed (121 frames).
    *   `execute_times`: Number of times the script will execute (-1, indefinitely).

This entity serves as a destructible container that can release materials and trigger an explosion when damaged or destroyed, with its behavior further modified by a Lua script.