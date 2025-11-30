---
title: Physics Fungus Big
category: entities
---

# Physics Fungus Big

This document describes the `physics_fungus_big.xml` entity, a large, physics-enabled mushroom prop in Noita. It details its physical properties, visual components, damage handling, and special behaviors like explosion and light emission.

## Core Components

### PhysicsBody2Component
Defines the physical properties of the fungus.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `is_static`      | `0`     | The body is not static and can be moved.        |
| `allow_sleep`    | `1`     | Allows the physics body to sleep when idle.     |
| `linear_damping` | `0.5`   | Reduces linear velocity over time.              |
| `init_offset_y`  | `52`    | Initial vertical offset of the physics body.    |

### PhysicsImageShapeComponent
These components define the visual shapes and collision areas of the fungus, composed of a cap and a stalk.

| Attribute    | Value                               | Description                                     |
| :----------- | :---------------------------------- | :---------------------------------------------- |
| `image_file` | `data/props_gfx/physics_fungus_cap_03.png` | Image for the fungus cap.                       |
| `image_file` | `data/props_gfx/physics_fungus_stalk.png` | Image for the fungus stalk segments.            |
| `image_file` | `data/props_gfx/physics_fungus_foot.png`  | Image for the fungus foot.                      |
| `material`   | `fungus_loose`                      | The material type for collision and physics.    |
| `offset_y`   | Varies                              | Vertical offset for each shape segment.         |

### MaterialInventoryComponent
Manages the material contained within the fungus.

| Attribute             | Value   | Description                                     |
| :-------------------- | :------ | :---------------------------------------------- |
| `on_death_spill`      | `1`     | Spills its contents when destroyed.             |
| `leak_on_damage_percent` | `1`     | Leaks material when damaged.                    |
| `kill_when_empty`     | `1`     | The entity is destroyed when its material is gone. |
| `count_per_material_type` | `blood_fungi` | The material contained is `blood_fungi`.        |
| `count`               | `1200`  | The amount of `blood_fungi` it contains.        |

### DamageModelComponent
Defines the health and damage-related properties of the fungus.

| Attribute                 | Value   | Description                                     |
| :------------------------ | :------ | :---------------------------------------------- |
| `hp`                      | `0.6`   | Hit points of the fungus.                       |
| `ragdoll_material`        | `fungus_loose_trippy` | Material used for its ragdoll.                  |
| `blood_material`          | `blood_fungi` | Material spilled upon damage/death.             |
| `blood_sprite_directional` | `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` | Sprite for directional blood splatters.         |
| `blood_sprite_large`      | `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` | Sprite for large blood splatters.               |
| `minimum_knockback_force` | `100000` | High force required to knock it back.           |

### ExplodeOnDamageComponent
Handles the explosion behavior when the fungus is damaged or destroyed.

| Attribute                     | Value   | Description                                     |
| :---------------------------- | :------ | :---------------------------------------------- |
| `explode_on_death_percent`    | `1`     | Explodes when its health reaches 0%.            |
| `physics_body_destruction_required` | `0.25`  | Explosion is more likely if physics body is significantly damaged. |
| `config_explosion.camera_shake` | `40`    | Intensity of camera shake during explosion.     |
| `config_explosion.explosion_radius` | `40`    | Radius of the explosion.                        |
| `config_explosion.load_this_entity` | `data/entities/particles/particle_explosion/main_pink.xml` | Entity to load for the explosion effect.        |
| `config_explosion.create_cell_material` | `fire`  | Material of the cells created by the explosion. |
| `config_explosion.spark_material` | `plasma_fading_pink` | Material of the sparks generated.               |
| `config_explosion.audio_event_name` | `explosions/slime` | Sound event played during the explosion.        |

## Other Notable Components

### PhysicsJoint2Component
These components define the revolute joints connecting the different segments of the fungus's stalk and attaching it to the ground.

*   **Stalk Joints (IDs 1-7):** Connect individual stalk segments, allowing for some flexibility.
    *   `type`: `REVOLUTE_JOINT`
    *   `break_force`: `10`
    *   `break_distance`: `5`
*   **Ground Joint (ID 8):** Attaches the fungus foot to the nearest surface.
    *   `type`: `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`
    *   `break_force`: `35`
    *   `break_distance`: `8`
    *   `ray_y`: `30` (Raycast distance for surface detection)

### LightComponent
Emits a light source.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `radius`  | `120` | The radius of the light.                        |
| `r`, `g`, `b` | `32`, `255`, `250` | The RGB color of the light (pinkish-white). |

### LuaComponent
Attaches a Lua script for custom behavior.

| Attribute         | Value                               | Description                                     |
| :---------------- | :---------------------------------- | :---------------------------------------------- |
| `script_source_file` | `data/scripts/props/physics_fungus.lua` | The Lua script controlling its behavior.        |
| `execute_every_n_frame` | `1`                                 | The script executes every frame.                |

### AudioLoopComponent
Plays a looping sound effect.

| Attribute   | Value                | Description                                     |
| :---------- | :------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/materials.bank` | The audio bank containing the sound.            |
| `event_name` | `materials/spray_fungus` | The specific sound event to play.               |