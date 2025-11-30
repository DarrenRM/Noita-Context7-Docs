---
title: Gold Orb Item
category: entities
---

# Gold Orb Item

This document details the configuration of the Gold Orb item in Noita, focusing on its physical properties, interaction mechanics, and visual effects for AI-assisted modding.

## Core Components

The Gold Orb is defined by several key components that dictate its behavior and appearance.

### PhysicsBodyComponent
Manages the physical presence of the orb in the game world.

| Attribute           | Value      | Description                                                              |
| :------------------ | :--------- | :----------------------------------------------------------------------- |
| `allow_sleep`       | `1`        | Allows the physics body to go to sleep when idle to save resources.      |
| `is_bullet`         | `1`        | Treats the entity as a projectile for physics interactions.              |
| `hax_fix_going_through_ground` | `1` | A specific fix to prevent the orb from clipping through the ground. |

### PhysicsImageShapeComponent
Defines the visual shape and material of the orb for physics simulation.

| Attribute   | Value                     | Description                                    |
| :---------- | :------------------------ | :--------------------------------------------- |
| `image_file`| `data/items_gfx/orb.png`  | The sprite used for the orb's physical shape.  |
| `material`  | `metal_hard`              | The physical material properties of the orb.   |

### ItemComponent
Handles the item-specific properties, such as its name, pickability, and inventory placement.

| Attribute           | Value                 | Description                                                              |
| :------------------ | :-------------------- | :----------------------------------------------------------------------- |
| `item_name`         | `$item_gold_orb`      | The internal name for the item, used for localization.                   |
| `is_pickable`       | `1`                   | Allows the player to pick up the item.                                   |
| `is_equipable_forced`| `1`                  | Forces the item to be equipped when picked up.                           |
| `ui_sprite`         | `data/ui_gfx/items/orb_gold.png` | The sprite displayed in the UI for this item.                          |
| `ui_description`    | `$itemdesc_gold_orb`  | The description text for the item, used for localization.                |
| `preferred_inventory`| `QUICK`               | The inventory tab where the item is preferentially placed.               |

### LuaComponent
Links the orb to its custom scripting logic.

| Attribute     | Value                       | Description                                     |
| :------------ | :-------------------------- | :---------------------------------------------- |
| `script_kick` | `data/scripts/items/gold_orb.lua` | The Lua script file that controls the orb's behavior. |

### PhysicsThrowableComponent
Enables the orb to be thrown by the player.

| Attribute         | Value | Description                               |
| :---------------- | :---- | :---------------------------------------- |
| `max_throw_speed` | `180` | The maximum speed the orb can be thrown.  |
| `throw_force_coeff`| `1.5` | A coefficient affecting throw force.      |

### SpriteParticleEmitterComponent
These components are responsible for generating visual particle effects associated with the orb.

*   **Shine Effects:** Multiple `SpriteParticleEmitterComponent` instances are used to create shimmering and glowing visual effects.
    *   `sprite_file`: Points to different shine particle definitions (e.g., `shine_07.xml`, `shine_08.xml`, `shine_06.xml`).
    *   `lifetime`: Controls how long individual particles last.
    *   `emission_interval_min_frames`/`max_frames`: Determines the frequency of particle emissions.
    *   `count_min`/`max`: Sets the number of particles emitted per burst.
    *   `additive`: Enables additive blending for brighter effects.
    *   `randomize_scale`, `randomize_position`, `randomize_animation_speed_coeff`: Introduce variation in particle appearance and behavior.

## Key Attributes for Modding

When modifying the Gold Orb, consider these attributes:

*   **`PhysicsBodyComponent`**: Adjust `linear_damping`, `angular_damping`, and `hax_fix_going_through_ground` to alter its physical response.
*   **`PhysicsImageShapeComponent`**: Change `image_file` to alter its visual representation. `material` affects its interaction with other physics objects.
*   **`ItemComponent`**: Modify `item_name`, `ui_sprite`, and `ui_description` for UI customization. `preferred_inventory` can change where it's stored.
*   **`LuaComponent`**: The `script_kick` attribute is crucial for defining custom behaviors by linking to different Lua scripts.
*   **`PhysicsThrowableComponent`**: Tweak `max_throw_speed` and `throw_force_coeff` to adjust throwing mechanics.
*   **`SpriteParticleEmitterComponent`**: Customize the visual flair by modifying `sprite_file`, `lifetime`, `count`, and randomization parameters for particle effects.

This structured documentation aims to provide a clear understanding of the Gold Orb's components and key attributes, facilitating easier integration and modification within Noita mods.