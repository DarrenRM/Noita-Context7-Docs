---
title: UI Icon Example Entity
category: entities
---

# UI Icon Example Entity

This entity serves as a template for creating UI icons within Noita, demonstrating how to associate visual elements with in-game functionality. It showcases components for displaying icons, handling physics, and integrating with Lua scripts for item behavior.

## Core Components

### UIIconComponent
This component defines the visual representation and descriptive text for the UI icon.

| Attribute        | Description                                     |
| :--------------- | :---------------------------------------------- |
| `icon_sprite_file` | Path to the sprite file for the icon.           |
| `name`           | The name displayed for the item/icon.           |
| `description`    | Textual description of the item's function.     |

### PhysicsBodyComponent
Defines the physical properties of the entity when it exists in the game world.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `uid`               | Unique identifier for the physics body.         |
| `allow_sleep`       | Whether the body can enter a sleep state.       |
| `is_bullet`         | If true, the body is treated as a projectile.   |
| `send_collision_messages` | Whether to send collision events.           |

### PhysicsImageShapeComponent
Defines the collision shape of the entity based on an image file.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `body_id`   | The ID of the `PhysicsBodyComponent` it's linked to. |
| `image_file`| The image file used to define the shape.        |
| `material`  | The physics material for collision properties.  |

### LuaComponent
Allows for custom scripting to define entity behavior.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `execute_on_added`    | If true, the script runs when the entity is added. |
| `remove_after_executed` | If true, the component is removed after execution. |
| `script_source_file`  | Path to the Lua script file.                    |
| `script_item_picked_up` | Script to execute when the item is picked up.   |

### PotionComponent
Specific component for potion-like entities, influencing their spray behavior.

| Attribute         | Description                                     |
| :---------------- | :---------------------------------------------- |
| `spray_velocity_coeff` | Coefficient for spray velocity.                 |

### MaterialInventoryComponent
Manages the material contents of the entity, including spilling and leaking.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `drop_as_item`        | If 0, does not drop as a separate item on death. |
| `on_death_spill`      | If true, spills contents on death.              |
| `leak_pressure_min`   | Minimum pressure for leaking.                   |
| `leak_on_damage_percent` | Percentage of damage that causes leaking.       |

### DamageModelComponent
Defines how the entity takes damage and its properties related to damage.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `hp`                  | Hit points of the entity.                       |
| `fire_damage_amount`  | Amount of damage taken from fire.               |
| `materials_that_damage` | Materials that can damage this entity.          |
| `materials_how_much_damage` | How much damage these materials inflict.        |

### ExplodeOnDamageComponent
Enables the entity to explode under certain damage conditions.

| Attribute                 | Description                                     |
| :------------------------ | :---------------------------------------------- |
| `explode_on_death_percent`| Percentage of damage that triggers explosion on death. |
| `physics_body_destruction_required` | Physics body destruction threshold for explosion. |

#### config_explosion
Configuration for the explosion effect.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `damage`            | Damage dealt by the explosion.                  |
| `camera_shake`      | Intensity of camera shake.                      |
| `explosion_radius`  | Radius of the explosion.                        |
| `ray_energy`        | Energy of the explosion's rays.                 |
| `physics_explosion_power.max` | Maximum physics force applied by the explosion. |

### ItemComponent
Marks the entity as an item that can be interacted with in the inventory and world.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `item_name`           | The internal name of the item.                  |
| `is_pickable`         | Whether the item can be picked up.              |
| `is_equipable_forced` | If true, forces equipping when picked up.       |
| `ui_sprite`           | Path to the UI sprite for the item.             |
| `ui_description`      | Description shown in the UI.                    |
| `preferred_inventory` | Default inventory to place the item in.         |

### AbilityComponent
Grants the entity specific abilities, such as throwing.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `throw_as_item` | If true, the item can be thrown.                |

### SpriteParticleEmitterComponent
Defines particle effects that are emitted by the entity.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `sprite_file`         | Path to the particle sprite.                    |
| `lifetime`            | Duration of the particle effect.                |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of the particles.                 |
| `color_change.r`, `color_change.g`, `color_change.b`, `color_change.a` | How the color changes over time.                |
| `scale.x`, `scale.y`  | Initial scale of the particles.                 |
| `scale_velocity.x`, `scale_velocity.y` | How the scale changes over time.                |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Frame interval for particle emission.           |
| `emissive`            | If true, particles emit light.                  |
| `additive`            | If true, particles use additive blending.       |
| `count_min`, `count_max` | Minimum and maximum number of particles emitted. |
| `randomize_position`  | Random offset for particle emission position.   |
| `randomize_velocity`  | Random initial velocity for particles.          |
| `velocity_always_away_from_center` | Particles are emitted away from the center. |