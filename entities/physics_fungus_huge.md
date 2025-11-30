---
title: Physics Fungus Huge
category: entities
---

# Physics Fungus Huge

This entity represents a large, physics-enabled fungus prop in Noita. It's designed to be destructible and interact with the game's physics engine.

## Key Components and Attributes

### PhysicsBody2Component
This component defines the physical properties of the fungus.

*   `is_static`: `0` - The body is not static and can be moved.
*   `allow_sleep`: `1` - The body can enter a sleep state when not in motion to save performance.
*   `angular_damping`: `0.01` - Controls how quickly rotational velocity decreases.
*   `linear_damping`: `0.5` - Controls how quickly linear velocity decreases.
*   `init_offset_y`: `70` - An initial vertical offset for the physics body.

### PhysicsImageShapeComponent
Multiple instances of this component define the visual shape and physical collision of the fungus, composed of a cap and a thick stalk.

*   `image_file`: Specifies the sprite for different parts of the fungus (e.g., `data/props_gfx/physics_fungus_cap_04.png`, `data/props_gfx/physics_fungus_stalk_thick.png`).
*   `material`: `fungus_loose` - The material type used for collision and interaction.
*   `offset_x`, `offset_y`: Define the position of each shape relative to the entity's origin.
*   `body_id`: Unique identifier for each physics shape.
*   `is_root`: `1` - Indicates the primary shape of the entity.

### PhysicsJoint2Component
These components create revolute joints, connecting different parts of the fungus to form a segmented stalk.

*   `type`: `REVOLUTE_JOINT` - Creates a joint that allows rotation.
*   `joint_id`: Links joints to their corresponding mutator components.
*   `body1_id`, `body2_id`: The IDs of the physics bodies being connected.
*   `break_force`: `10` - The force required to break the joint.
*   `break_distance`: `5` - The distance at which the joint breaks.

### PhysicsJoint2Component (Ground Attachment)
This component attaches the base of the fungus to the environment.

*   `type`: `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` - Attaches the body to the closest surface.
*   `body1_id`: `110` - The ID of the physics body to attach (the foot of the fungus).
*   `break_force`: `35` - The force required to break the attachment.
*   `break_distance`: `8` - The distance at which the attachment breaks.
*   `ray_x`, `ray_y`: Define the raycast used to find a surface to attach to.

### MaterialInventoryComponent
Manages the internal material of the fungus.

*   `on_death_spill`: `1` - The material spills out when the entity dies.
*   `leak_on_damage_percent`: `1` - The material leaks when damaged.
*   `count_per_material_type`:
    *   `Material material="blood_fungi" count="1200"` - The fungus contains 1200 units of `blood_fungi` material.

### DamageModelComponent
Defines the health and damage-related properties of the fungus.

*   `hp`: `0.8` - The hit points of the fungus.
*   `ragdoll_material`: `fungus_loose_trippy` - The material used for the ragdoll effect upon death.
*   `blood_material`: `blood_fungi` - The material that spills out as blood.
*   `damage_multipliers`:
    *   `fire="40.0"` - Takes significantly more damage from fire.

### ExplodeOnDamageComponent
Handles the explosion behavior when the fungus is damaged or destroyed.

*   `explode_on_death_percent`: `1` - Explodes when health reaches 0%.
*   `physics_body_destruction_required`: `0.25` - Requires at least 25% of its physics body to be destroyed for explosion.
*   `config_explosion`: Contains detailed parameters for the explosion.
    *   `explosion_radius`: `60`
    *   `damage`: `5.5`
    *   `physics_explosion_power.min`: `0.8`
    *   `physics_explosion_power.max`: `1.8`
    *   `spark_material`: `plasma_fading_pink`
    *   `audio_event_name`: `explosions/slime`

### LightComponent
Adds a light source to the fungus.

*   `radius`: `120`
*   `r`, `g`, `b`: `32`, `255`, `250` - A greenish-blue light.

### LuaComponent
Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/props/physics_fungus.lua` - The script controlling its behavior.
*   `execute_every_n_frame`: `1` - The script runs every frame.

### VariableStorageComponent
Stores custom variables.

*   `name`: `lift`
*   `value_int`: `-60` - Likely used by the Lua script for some effect.

### AudioLoopComponent
Plays a looping sound effect.

*   `event_name`: `materials/spray_fungus` - A sound associated with spraying fungus.