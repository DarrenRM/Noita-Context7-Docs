---
title: Safe Haven Item
category: entities
---

# Safe Haven Item

This document details the configuration of the "Safe Haven" item entity in Noita, focusing on its attributes and behaviors relevant to AI-assisted modding.

## Core Entity Configuration

The Safe Haven item is built upon a base entity for projectiles, inheriting its fundamental physics and interaction properties.

```xml
<Entity tags="hittable,teleportable_NOT,item_physics" >
	<Base file="data/entities/base_item_projectile.xml" />
    <!-- ... other components ... -->
</Entity>
```

*   **`tags`**: Defines key interactions. `hittable` and `item_physics` indicate it can be struck and interacts physically. `teleportable_NOT` explicitly prevents teleportation.

## Physics Components

These components govern the item's physical presence and behavior in the game world.

### `PhysicsBodyComponent`

Manages the physical properties of the item.

*   **`uid`**: Unique identifier for the physics body.
*   **`allow_sleep`**: Allows the body to enter a sleep state when inactive to save performance.
*   **`angular_damping`**: Reduces rotational velocity over time.
*   **`linear_damping`**: Reduces linear velocity over time.
*   **`is_bullet`**: Indicates it's treated as a projectile for collision purposes.
*   **`on_death_leave_physics_body`**: Ensures physics properties persist even if the entity is "killed" or removed.
*   **`hax_fix_going_through_ground`**: A specific fix to prevent it from falling through terrain.

### `PhysicsImageShapeComponent`

Defines the visual shape and material for physics interactions.

*   **`image_file`**: Specifies the sprite used for the item's visual representation.
*   **`material`**: Sets the physics material, influencing how it interacts with other physics objects (e.g., `item_box2d_glass`).

### `PhysicsThrowableComponent`

Enables the item to be thrown.

*   **`max_throw_speed`**: The maximum velocity achievable when thrown.
*   **`throw_force_coeff`**: A multiplier for the force applied when throwing.
*   **`min_torque` / `max_torque`**: Defines the range of rotational force applied when thrown.

### `VelocityComponent`

Manages the item's velocity.

## Functionality Components

These components define the unique behaviors of the Safe Haven item.

### `VariableStorageComponent`

Used to store custom variables associated with the entity.

*   **`name="player_hp"`**: Stores a float value representing player health.
    *   **`value_float="4.0"`**: The initial value for player health.
*   **`name="throw_time"`**: Stores an integer value related to throwing.
    *   **`value_int="-1"`**: Initial value, likely indicating not yet thrown or a specific state.

### `LuaComponent`

Executes custom Lua scripts to implement game logic.

*   **`script_source_file="data/scripts/items/safe_haven_spawn.lua"`**: This script handles the item's spawning behavior and initial setup.
    *   **`execute_every_n_frame="1"`**: The script runs every frame.
*   **`script_throw_item="data/scripts/items/safe_haven_throw.lua"`**: This script manages the item's behavior when thrown.
    *   **`execute_every_n_frame="-1"`**: This indicates the script is likely triggered by specific events rather than a continuous frame execution.

## Item and UI Components

These components define how the item is presented and interacted with in the game's inventory and UI.

### `SpriteComponent`

Defines the visual sprite when the item is held by the player.

*   **`_tags="enabled_in_hand"`**: This sprite is active only when the item is in the player's hand.
*   **`_enabled="0"`**: The sprite is initially disabled, likely activated by game logic.
*   **`image_file`**: The sprite asset for the item in hand.

### `ItemComponent`

Defines the item's properties as an inventory item.

*   **`item_name="$item_safe_haven"`**: The internal name for the item, likely linked to localization.
*   **`is_pickable="1"`**: Allows the item to be picked up by the player.
*   **`is_equipable_forced="1"`**: The item can be equipped directly.
*   **`ui_sprite`**: The sprite displayed in the UI for this item.
*   **`ui_description="$item_description_safe_haven"`**: The description text, linked to localization.
*   **`preferred_inventory="QUICK"`**: Suggests it should be placed in the quick inventory.

### `UIInfoComponent`

Provides information for UI elements.

*   **`name="$item_safe_haven"`**: The name displayed in UI elements.

## Visual Effects (FX)

### `ParticleEmitterComponent`

Manages particle effects, specifically when the item is thrown.

*   **`_tags="enabled_on_throw"`**: Particles are emitted only when the item is thrown.
*   **`emitted_material_name="spark_green"`**: The type of particle to emit.
*   **`lifetime_min`/`lifetime_max`**: Duration of individual particles.
*   **`count_min`/`count_max`**: Number of particles emitted.
*   **`area_circle_radius.min`/`max`**: The radius of the emission area.
*   **`is_emitting="1"`**: Enables the particle emitter.

### `LightComponent`

Adds a light source to the item.

*   **`_tags="enabled_in_world,enabled_in_hand"`**: The light is active when the item is in the world or in hand.
*   **`radius`**: The range of the light.
*   **`r`, `g`, `b`**: The color components of the light (green in this case).

## Ability Component

### `AbilityComponent`

Grants the entity specific abilities.

*   **`ui_name="$item_safe_haven"`**: The name associated with the ability in the UI.
*   **`throw_as_item="1"`**: Configures the item to be thrown as a projectile.
*   **`gun_config`**: Specific configuration for projectile-like behavior.
    *   **`deck_capacity="0"`**: Indicates no capacity for a deck of spells, typical for thrown items.