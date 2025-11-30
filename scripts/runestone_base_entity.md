---
title: Runestone Base Entity
category: data/entities
---

# Runestone Base Entity

This document describes the base configuration for a runestone item in Noita, focusing on its core attributes and behaviors. Runestones are special items that can be picked up, thrown, and activated to trigger unique effects.

## Core Components

This section highlights the most important components that define a runestone's functionality.

### `PhysicsBodyComponent`

Manages the physical properties of the runestone in the game world.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `uid`               | Unique identifier for the physics body.                                  |
| `allow_sleep`       | Allows the physics body to go to sleep when inactive to save resources.  |
| `angular_damping`   | Resistance to rotational movement.                                       |
| `fixed_rotation`    | Prevents the object from rotating.                                       |
| `is_bullet`         | Marks the object as a projectile or something that moves dynamically.    |
| `linear_damping`    | Resistance to linear movement.                                           |
| `hax_fix_going_through_ground` | A specific fix to prevent the object from clipping through the ground. |

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the runestone.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `body_id`     | Links this shape to a specific `PhysicsBodyComponent`.                   |
| `centered`    | Centers the image on the physics body.                                   |
| `image_file`  | Path to the sprite used for the runestone's visual appearance.           |
| `material`    | The physical material properties for collision and interaction.          |

### `LuaComponent` (Activation)

This component is crucial for defining the runestone's active effect when used.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `_tags`             | Specifies when this component is active (e.g., `activate`).              |
| `script_source_file`| Path to the Lua script that handles the runestone's unique effect.       |
| `execute_every_n_frame` | How often the script logic is executed (e.g., `10` frames).            |
| `_enabled`          | Controls whether the component is active (e.g., `0` for disabled by default). |

### `ItemComponent`

Defines the runestone as an item that can be interacted with by the player.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `_tags`                 | Standard item tags, including `enabled_in_world`.                        |
| `item_name`             | The internal name of the item, often linked to localization strings.     |
| `max_child_items`       | Maximum number of child items that can be stacked.                       |
| `is_pickable`           | Allows the player to pick up the item.                                   |
| `is_equipable_forced`   | Forces the item to be equipped when picked up.                           |
| `ui_sprite`             | Path to the sprite displayed in the player's UI/inventory.               |
| `ui_description`        | Localization string for the item's description in the UI.                |
| `preferred_inventory`   | The inventory slot the item prefers (e.g., `QUICK`).                     |

### `AbilityComponent`

Grants the runestone specific abilities, such as being thrown.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `ui_name`     | The name displayed in the UI for this ability.                           |
| `throw_as_item` | Indicates that this item can be thrown.                                  |

## Interaction and Behavior

This section details how the runestone behaves in different game states.

### Throwing and Physics

*   **`PhysicsThrowableComponent`**: Configures how the runestone is thrown, including `max_throw_speed` and `throw_force_coeff`.
*   **`PhysicsBodyCollisionDamageComponent`**: Applies damage to other entities if the runestone collides with them at a sufficient speed (`speed_threshold`).

### Activation and Visuals

*   **`LuaComponent` (script_kick/script_throw_item)**: These components often point to `runestone_activate.lua` and handle the initial logic when the runestone is kicked or thrown.
*   **`VariableStorageComponent`**: Used to store state variables, such as `active` (an integer, likely `0` or `1`).
*   **`SpriteComponent`**: Defines the visual appearance of the runestone when held in the player's hand (`_tags="enabled_in_hand"`).
*   **`ParticleEmitterComponent`**: Responsible for generating visual effects (particles) when the runestone is activated. It specifies the `emitted_material_name`, lifetime, count, and emission patterns.
*   **`AudioLoopComponent`**: Plays sound effects associated with the runestone's activation, including a looping sound event.

### Player Interaction

*   **`LuaComponent` (script_item_picked_up)**: This component, often linked to `runestone_activate.lua`, handles logic that occurs specifically when the player picks up the runestone.

## Example Usage (Conceptual)

A typical runestone would have a unique Lua script (`runestone_slow.lua` in this example) that is triggered by the `LuaComponent` with the `activate` tag. This script would then implement the specific effect of that runestone (e.g., slowing down enemies). The `ItemComponent` and `UIInfoComponent` ensure it's properly displayed and described in the game's UI.