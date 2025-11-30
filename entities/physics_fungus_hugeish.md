---
title: Physics Fungus (Hugeish)
category: entities
---

# Physics Fungus (Hugeish)

This entity represents a large, physics-enabled fungus prop that can be interacted with in the game world. It's composed of multiple physics bodies and joints, giving it a flexible and somewhat unstable structure. When damaged, it can leak a fungal blood material and eventually explode.

## Key Components and Attributes

### PhysicsBody2Component
This component defines the primary physics properties of the fungus.

*   `is_static`: `0` - The fungus is not static and can be moved.
*   `allow_sleep`: `1` - Allows the physics body to enter a sleep state when not in motion, optimizing performance.
*   `angular_damping`: `0.01` - Controls how quickly rotational velocity decreases.
*   `linear_damping`: `0.5` - Controls how quickly linear velocity decreases.
*   `init_offset_y`: `48` - The initial vertical offset of the physics body.

### PhysicsImageShapeComponent
These components define the visual and physical shapes of the fungus, broken down into multiple parts (cap, stalk, foot).

*   `image_file`: Specifies the sprite for each part (e.g., `data/props_gfx/physics_fungus_cap_04.png`).
*   `material`: `fungus_loose` - The material used for collision and interaction.
*   `body_id`: Unique identifier for each physics body.
*   `offset_x`, `offset_y`: Position of the shape relative to its parent body.
*   `is_root`: `1` - Indicates the main, root physics body.

### PhysicsJoint2Component
These components connect the various `PhysicsImageShapeComponent` bodies, creating the fungus's structure.

*   `type`: `REVOLUTE_JOINT` - Creates a joint that allows rotation.
*   `joint_id`: Links joints to their corresponding mutator components.
*   `body1_id`, `body2_id`: The IDs of the physics bodies being connected.
*   `offset_x`, `offset_y`: The position of the joint relative to `body1_id`.
*   `break_force`: The force required to break the joint.
*   `break_distance`: The distance at which the joint will break.

A special `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` is used to anchor the fungus to the ground.

### MaterialInventoryComponent
Manages the internal materials of the fungus.

*   `drop_as_item`: `0` - The fungus does not drop as a collectible item.
*   `on_death_spill`: `1` - Spills its contents upon death.
*   `leak_on_damage_percent`: `1` - Leaks when damaged.
*   `kill_when_empty`: `1` - The entity is destroyed when its material is depleted.
*   `count_per_material_type`:
    *   `Material material="blood_fungi" count="1200"`: The fungus contains 1200 units of `blood_fungi` material.

### DamageModelComponent
Defines how the fungus takes damage and its reactions.

*   `hp`: `0.8` - The health points of the fungus.
*   `ragdoll_material`: `fungus_loose_trippy` - The material used for its ragdoll effect upon death.
*   `blood_material`: `blood_fungi` - The material that spills when damaged.
*   `damage_multipliers`:
    *   `fire="40.0"`: Takes significantly more damage from fire.

### ExplodeOnDamageComponent
Handles the explosion behavior of the fungus.

*   `explode_on_death_percent`: `1` - Explodes when health reaches 0%.
*   `explode_on_damage_percent`: `0.0` - Does not explode solely based on damage percentage (unless it leads to death).
*   `physics_body_modified_death_probability`: `0.9` - High chance of exploding if its physics body is modified upon death.
*   `physics_body_destruction_required`: `0.25` - Requires at least 25% of its physics body to be destroyed for explosion chance.
*   `config_explosion`: Contains detailed parameters for the explosion effect, including radius, sprite, damage, and particle effects.

### LightComponent
Adds a light source to the fungus.

*   `radius`: `120` - The range of the light.
*   `r`, `g`, `b`: `32`, `255`, `250` - Defines the light color as a bright cyan/pink.

### LuaComponent
Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/props/physics_fungus.lua` - The script controlling its dynamic behavior.
*   `execute_every_n_frame`: `1` - The script runs every frame.

### AudioLoopComponent
Plays a looping sound effect.

*   `event_name`: `materials/spray_fungus` - The sound event triggered.