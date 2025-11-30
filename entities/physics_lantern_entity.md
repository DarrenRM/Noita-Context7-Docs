---
title: Physics Lantern Entity
category: entities
---

# Physics Lantern Entity

This document describes the `physics_lantern.xml` entity, a physics-enabled prop in Noita that can be damaged, explode, and spill its contents.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits core physics and item properties.

### Physics Components

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/props_gfx/lantern.png` - Defines the visual appearance of the lantern.
    *   `material`: `glass_box2d` - Sets the physics material for collision and interaction.
*   **`PhysicsBodyComponent`**:
    *   `allow_sleep`: `1` - Allows the body to enter a sleep state when inactive to save performance.
    *   `angular_damping`: `0.01` - Reduces rotational velocity over time.
    *   `linear_damping`: `0.1` - Reduces linear velocity over time.
*   **`PhysicsJointComponent`**:
    *   `nail_to_wall`: `1` - Attaches the lantern to a wall, preventing it from falling freely.
    *   `pos_x`, `pos_y`: Defines the attachment point relative to the entity's origin.
*   **`PhysicsBodyCollisionDamageComponent`**:
    *   `speed_threshold`: `120.0` - The speed at which collisions start to deal damage.

### Interaction and Damage

*   **`LightComponent`**:
    *   `radius`: `240` - The radius of the light emitted by the lantern.
*   **`MaterialInventoryComponent`**:
    *   `drop_as_item`: `0` - The lantern does not drop as a usable item upon death.
    *   `on_death_spill`: `1` - Contents are spilled when the lantern dies.
    *   `leak_on_damage_percent`: `0.999` - Leaks contents when nearly destroyed.
    *   **`count_per_material_type`**:
        *   `Material material="oil" count="5"`: The lantern contains 5 units of "oil".
*   **`DamageModelComponent`**:
    *   `falling_damage_damage_max`, `falling_damage_damage_min`: Defines the range of damage from falling.
    *   `falling_damage_height_max`, `falling_damage_height_min`: Defines the height range for falling damage.
    *   `fire_damage_amount`: `0.2` - The amount of damage taken from fire.
    *   `hp`: `0.9` - The health of the lantern.
*   **`ExplodeOnDamageComponent`**:
    *   `explode_on_death_percent`: `1` - The lantern will explode when it dies.
    *   `explode_on_damage_percent`: `0.0` - The lantern will explode immediately upon taking any damage.
    *   **`config_explosion`**:
        *   `damage`: `1` - The base damage of the explosion.
        *   `camera_shake`: `2` - The intensity of camera shake during the explosion.
        *   `explosion_radius`: `12` - The radius of the explosion's effect.
        *   `explosion_sprite`: `data/particles/explosion_008.xml` - The visual effect of the explosion.
        *   `hole_enabled`: `1` - Creates holes in the environment.
        *   `ray_energy`: `10000` - The energy of the explosion's damaging rays.
        *   `damage_mortals`: `1` - The explosion damages other entities.
        *   `sparks_count_max`, `sparks_count_min`: Defines the range of sparks created.

### Visuals and Animation

*   **`SpriteComponent`**:
    *   `image_file`: `data/props_gfx/lantern_flame.xml` - The sprite for the lantern's flame.
    *   `offset_x`, `offset_y`: Positions the flame sprite relative to the lantern.
    *   `rect_animation`: `stand` - Specifies the default animation state.
    *   `z_index`: `-1` - Renders the flame behind the lantern body.
*   **`SpriteAnimatorComponent`**: Handles sprite animations.

### Scripting and Audio

*   **`LuaComponent`**:
    *   `script_physics_body_modified`: `data/scripts/props/physics_lantern_damaged.lua` - Script executed when the physics body is modified (e.g., damaged).
    *   `script_death`: `data/scripts/props/lantern_death.lua` - Script executed when the lantern dies.
*   **`AudioComponent`**:
    *   `file`: `data/audio/Desktop/materials.bank` - The audio bank containing lantern sounds.
    *   `event_root`: `collision/lantern` - The root event for collision sounds.