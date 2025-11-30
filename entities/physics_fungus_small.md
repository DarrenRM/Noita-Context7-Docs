---
title: Physics Fungus Small
category: entities
---

# Physics Fungus Small

This entity represents a small, physics-enabled fungus prop. It's designed to be breakable and interact with the game's physics engine, potentially spilling its contents when damaged.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the fungus.

*   `is_static`: `0` - The fungus is not fixed in place and can move.
*   `allow_sleep`: `1` - Allows the physics body to enter a sleep state when inactive to save performance.
*   `linear_damping`: `0.3` - Reduces linear velocity over time.
*   `init_offset_y`: `28` - Initial vertical offset for the physics body.

### PhysicsImageShapeComponent
Defines the visual and physical shape of the fungus using images. Multiple components are used to construct the fungus's cap and stalk.

*   `image_file`: Specifies the sprite for the component (e.g., `physics_fungus_cap_02.png`, `physics_fungus_stalk.png`).
*   `material`: `fungus_loose` - The material type used for physics interactions.
*   `body_id`: Unique identifier for each physics shape.
*   `is_root`: `1` - Indicates the primary shape of the entity.
*   `offset_x`, `offset_y`: Position of the shape relative to its parent.

### PhysicsJoint2Component
Connects different parts of the fungus or attaches it to the environment.

*   `type`: `REVOLUTE_JOINT` for connecting parts, `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` for ground attachment.
*   `joint_id`: Identifies the joint.
*   `body1_id`, `body2_id`: The IDs of the physics bodies being connected.
*   `break_force`: The force required to break the joint.
*   `break_distance`: The distance at which the joint breaks.
*   `offset_x`, `offset_y`: Offset for the joint's connection point.
*   `ray_x`, `ray_y`: Used for surface attachment joints to determine the surface.

### MaterialInventoryComponent
Manages the materials contained within the fungus.

*   `drop_as_item`: `0` - The fungus does not drop as an item upon death.
*   `on_death_spill`: `1` - Spills its contents when destroyed.
*   `leak_on_damage_percent`: `1` - Leaks when damaged.
*   `leak_pressure_min`, `leak_pressure_max`: Defines the pressure range for leaking.
*   `kill_when_empty`: `1` - The entity is destroyed when its material inventory is depleted.
*   `count_per_material_type`:
    *   `Material material="blood_fungi" count="500"`: Contains 500 units of `blood_fungi` material.

### DamageModelComponent
Defines how the fungus takes damage and reacts.

*   `hp`: `0.6` - Hit points of the fungus.
*   `air_needed`: `0` - Does not require air.
*   `ragdoll_material`: `fungus_loose_trippy` - Material used for ragdoll effects.
*   `blood_material`: `blood_fungi` - Material spilled upon damage.
*   `blood_sprite_directional`, `blood_sprite_large`: Sprites for blood splatters.
*   `minimum_knockback_force`: `100000` - High knockback resistance.
*   `damage_multipliers`:
    *   `fire="40.0"`: Takes significantly more damage from fire.

### ExplodeOnDamageComponent
Handles explosion effects when the fungus is damaged or destroyed.

*   `explode_on_death_percent`: `1` - Explodes when health reaches 0.
*   `physics_body_modified_death_probability`: `0.9` - High probability of exploding when its physics body is modified upon death.
*   `physics_body_destruction_required`: `0.25` - Requires 25% of its physics body to be destroyed to trigger explosion.
*   `config_explosion`: Contains detailed settings for the explosion:
    *   `camera_shake`: `40` - Amount of camera shake.
    *   `explosion_radius`: `20` - Radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_025_fuel.xml` - Sprite for the explosion.
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_pink.xml` - Entity to load for the explosion effect.
    *   `create_cell_material`: `fire` - Creates fire cells.
    *   `physics_explosion_power`: `min="0.8" max="1.8"` - Force of the physics-based explosion.
    *   `spark_material`: `plasma_fading_pink` - Material for sparks.
    *   `audio_event_name`: `explosions/slime` - Sound event for the explosion.

### LightComponent
Adds a light source to the entity.

*   `radius`: `50` - The radius of the light.
*   `r`, `g`, `b`: `32`, `255`, `250` - Color of the light (pinkish-white).

### LuaComponent
Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/props/physics_fungus.lua` - The script controlling its behavior.
*   `execute_every_n_frame`: `1` - Executes the script every frame.

### AudioLoopComponent
Plays a looping sound effect.

*   `file`: `data/audio/Desktop/materials.bank` - The audio bank containing the sound.
*   `event_name`: `materials/spray_fungus` - The specific sound event to play.