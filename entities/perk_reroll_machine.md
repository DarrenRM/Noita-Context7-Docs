---
title: Perk Reroll Machine
category: entities
---

# Perk Reroll Machine

This entity represents the Perk Reroll Machine found in Noita. It allows players to reroll their available perks for a cost.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_shop_item.xml"`**: Inherits functionality from the generic shop item, providing core mechanics for shop interactions.

### Item Components

*   **`ItemCostComponent cost="400"`**: Defines the cost of this item in the game's currency.
*   **`UIInfoComponent name="$item_perk_reroll"`**: Sets the display name for the item in the UI.
*   **`ItemComponent`**:
    *   `_tags="perk_reroll_disable"`: This tag likely prevents the machine from being picked up or interacted with in unintended ways.
    *   `item_name="$item_perk_reroll"`: Links to the UI name.
    *   `play_spinning_animation="0"`: Disables a default spinning animation.
    *   `play_pick_sound="0"`: Disables a default pickup sound.
    *   `stats_count_as_item_pick_up="0"`: Ensures this doesn't count as a standard item pickup for progression.
    *   `auto_pickup="0"`: Prevents automatic pickup by the player.

### Physics and Sprite

*   **`VelocityComponent`**: Allows the entity to have velocity, though likely not used for this static object.
*   **`SimplePhysicsComponent`**: Provides basic physics properties.
*   **`SpriteComponent`**:
    *   `image_file="data/buildings_gfx/perk_reroll.png"`: Specifies the visual asset for the machine.
    *   `offset_x="10"`, `offset_y="39"`: Adjusts the sprite's position.
    *   `z_index="20"`: Controls the rendering layer.

### Scripting

*   **`LuaComponent script_item_picked_up="data/scripts/perks/perk_reroll.lua"`**: This script is executed when the item is "picked up" (interacted with), handling the perk reroll logic.
*   **`LuaComponent script_source_file="data/scripts/perks/perk_reroll_init.lua"`**: This script is executed when the entity is added to the world, likely for initialization tasks related to the perk reroll functionality.

### Visual Effects

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="spark_green"`: The type of particle emitted.
    *   `lifetime_min="4"`, `lifetime_max="8"`: Duration of emitted particles.
    *   `x_vel_min="-5"`, `x_vel_max="5"`, `y_vel_min="-20"`, `y_vel_max="5"`: Velocity parameters for particles.
    *   `count_min="4"`, `count_max="8"`: Number of particles emitted per burst.
    *   `emission_interval_min_frames="30"`, `emission_interval_max_frames="30"`: Controls the frequency of particle emissions.
    *   `area_circle_radius.max="11"`: The radius of the emission area.
    *   `is_emitting="1"`: Enables particle emission.