---
title: Small Lantern Prop
category: entities
---

# Small Lantern Prop

This document details the configuration for a small lantern prop entity in Noita, focusing on its physics, visual representation, and interactive components.

## Core Entity Properties

*   **`tags`**: `mortal`, `prop`, `prop_physics`
    *   `mortal`: Essential for the entity to be able to explode.
    *   `prop`, `prop_physics`: Identifies it as a physics-enabled prop.
*   **`serialize`**: `1` (Indicates the entity should be serialized).

## Key Components

### PhysicsBody2Component

Manages the physical properties of the lantern.

*   **`allow_sleep`**: `1` (Allows the physics body to enter a sleep state when inactive).
*   **`angular_damping`**: `0.01` (Resistance to rotational movement).
*   **`linear_damping`**: `0.1` (Resistance to linear movement).
*   **`init_offset_x`**: `3.5`, **`init_offset_y`**: `4` (Initial offset for the physics body).
*   **`root_offset_x`**: `5`, **`root_offset_y`**: `7` (Offset for the root of the physics body).

### PhysicsImageShapeComponent

Defines the visual shape and material for the physics body.

*   **`body_id`**: `0` (References the physics body).
*   **`image_file`**: `data/props_gfx/lantern_small.png` (The sprite used for the lantern's shape).
*   **`material`**: `glass_box2d` (The physics material, influencing interactions).
*   **`is_root`**: `1` (Marks this as the root shape).

### PhysicsJoint2Component

Attaches the lantern to nearby surfaces.

*   **`type`**: `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` (Specifies the joint type for attachment).
*   **`break_force`**: `0.5` (The force at which the joint will break).
*   **`break_on_body_modified`**: `1` (The joint breaks if the attached body is modified).
*   **`offset_x`**: `4.75`, **`offset_y`**: `3.5` (Offset for the joint attachment point).
*   **`body1_id`**: `0` (The physics body to which the joint is attached).

### LightComponent

Provides illumination.

*   **`_enabled`**: `1` (The light component is active).
*   **`radius`**: `240` (The radius of the light emitted).

### MaterialInventoryComponent

Manages the materials contained within the lantern.

*   **`_enabled`**: `1` (The component is active).
*   **`drop_as_item`**: `0` (The lantern does not drop its contents as an item upon destruction).
*   **`on_death_spill`**: `1` (Contents are spilled when the lantern is destroyed).
*   **`leak_on_damage_percent`**: `0.999` (Contents leak when 99.9% damaged).
*   **`count_per_material_type`**:
    *   `Material material="oil" count="4"` (Contains 4 units of oil).

### DamageModelComponent

Defines how the lantern takes damage and its health.

*   **`air_needed`**: `0` (Does not require air).
*   **`blood_material`**: `oil` (The material associated with damage effects).
*   **`falling_damage_damage_max`**: `1.2` (Maximum damage from falling).
*   **`falling_damage_damage_min`**: `0.1` (Minimum damage from falling).
*   **`falling_damage_height_max`**: `250` (Maximum height for falling damage calculation).
*   **`falling_damage_height_min`**: `70` (Minimum height for falling damage calculation).
*   **`falling_damages`**: `0` (Falling damage is not directly applied, likely handled by other components).
*   **`fire_damage_amount`**: `0.2` (Amount of damage from fire).
*   **`fire_probability_of_ignition`**: `0` (Cannot ignite from fire).
*   **`hp`**: `0.15` (Health points of the lantern).
*   **`critical_damage_resistance`**: `1` (Has full resistance to critical damage).
*   **`ui_report_damage`**: `0` (Does not report damage to the UI).

### ExplodeOnDamageComponent

Handles the explosion behavior when damaged.

*   **`explode_on_death_percent`**: `1` (Explodes when health reaches 0%).
*   **`explode_on_damage_percent`**: `0.0` (Explodes immediately upon taking any damage).
*   **`physics_body_modified_death_probability`**: `0.75` (75% chance to explode if physics body is modified).
*   **`physics_body_destruction_required`**: `0.5` (Explosion triggered if 50% of physics body is destroyed).
*   **`config_explosion`**:
    *   **`damage`**: `0.2` (Damage dealt by the explosion).
    *   **`camera_shake`**: `1` (Triggers camera shake).
    *   **`explosion_radius`**: `5` (Radius of the explosion).
    *   **`explosion_sprite`**: `data/particles/explosion_008.xml` (Particle effect for the explosion).
    *   **`explosion_sprite_lifetime`**: `8` (Duration of the explosion particle effect).
    *   **`create_cell_probability`**: `50` (Chance to create cells).
    *   **`hole_enabled`**: `1` (Creates holes in terrain).
    *   **`ray_energy`**: `10000` (Energy of the explosion rays).
    *   **`particle_effect`**: `1` (Enables particle effects).
    *   **`damage_mortals`**: `1` (Deals damage to mortals).
    *   **`physics_explosion_power.min`**: `0.05`, **`physics_explosion_power.max`**: `0.1` (Minimum and maximum physics force of the explosion).
    *   **`physics_throw_enabled`**: `1` (Objects are thrown by the explosion).
    *   **`shake_vegetation`**: `1` (Shakes vegetation).
    *   **`sparks_count_min`**: `5`, **`sparks_count_max`**: `10` (Number of sparks generated).
    *   **`stains_enabled`**: `1` (Creates stains).
    *   **`stains_radius`**: `10` (Radius of the stains).

### PhysicsBodyCollisionDamageComponent

Applies damage based on collision speed.

*   **`speed_threshold`**: `120.0` (Minimum speed for collision damage to occur).

### SpriteComponent

Defines the visual sprite for the flame.

*   **`image_file`**: `data/props_gfx/lantern_small_flame.xml` (The sprite for the flame).
*   **`offset_x`**: `5`, **`offset_y`**: `7` (Offset for the flame sprite).
*   **`z_index`**: `-1` (Renders the flame behind other elements).

### TorchComponent

Enables torch-like behavior.

*   **`_tags`**: `enabled_in_world` (Active when in the game world).

### SpriteAnimatorComponent

Handles sprite animations.

### LuaComponent (script_physics_body_modified)

*   **`script_physics_body_modified`**: `data/scripts/props/physics_lantern_damaged.lua` (Script executed when the physics body is modified).

### LuaComponent (script_death)

*   **`script_death`**: `data/scripts/props/lantern_small_death.lua` (Script executed when the lantern dies).

### AudioComponent

Manages sound effects.

*   **`file`**: `data/audio/Desktop/materials.bank` (Audio bank file).
*   **`event_root`**: `collision/lantern` (Root event for lantern-related sounds).