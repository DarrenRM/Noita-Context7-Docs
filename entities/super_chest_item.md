---
title: Super Chest Item
category: entities
---

# Super Chest Item

This document describes the `chest_random_super.xml` entity, which represents a special type of chest in Noita that contains random, powerful items.

## Core Components

This entity utilizes several key components to define its behavior and appearance:

*   **`UIInfoComponent`**: Defines the in-game name of the item.
    *   `name`: "$item_chest_treasure_super" - This is a localization key for the chest's name.
*   **`PhysicsBodyComponent`**: Governs the physical properties of the chest.
    *   `is_bullet`: "1" - Allows the chest to interact with physics as a projectile.
    *   `auto_clean`: "1" - The chest will be automatically removed when it's no longer needed.
    *   `hax_fix_going_through_ground`: "1" - A fix to prevent the chest from falling through the ground.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation and collision shape of the chest.
    *   `image_file`: "data/buildings_gfx/chest_random_super.png" - The sprite used for the chest.
    *   `material`: "wood_prop" - The material type, influencing its interaction with other game elements.
*   **`ItemComponent`**: Marks this entity as an item that can be picked up.
    *   `custom_pickup_string`: "$itempickup_open" - The text displayed when the player interacts with the chest to open it.
*   **`LuaComponent`**: Executes Lua scripts to define custom behavior.
    *   `script_physics_body_modified`: "data/scripts/items/chest_random_super.lua" - This script is executed when the physics body is modified, likely for opening logic.
    *   `script_item_picked_up`: "data/scripts/items/chest_random_super.lua" - This script is executed when the item is picked up, triggering the item generation.
*   **`LightComponent`**: Adds a light source to the chest.
    *   `r`, `g`, `b`: "255" - Sets the light color to white.
    *   `radius`: "64" - The range of the light.
    *   `fade_out_time`: "0.75" - How long the light takes to fade out.
*   **`ParticleEmitterComponent`**: Creates visual particle effects.
    *   `emitted_material_name`: "spark_yellow" - The type of particles emitted.
    *   `lifetime_min`/`max`: "1" to "3" - Duration of each particle.
    *   `x_vel_min`/`max`, `y_vel_min`/`max`: Defines the initial velocity of the particles, creating an outward burst.
    *   `count_min`/`max`: "4" to "12" - The number of particles emitted per burst.
    *   `emission_interval_min_frames`/`max_frames`: "12" - Controls the rate of particle emission.
    *   `area_circle_radius.max`: "11" - The radius of the area from which particles are emitted.
    *   `is_emitting`: "1" - Ensures the particle emitter is active.

## Key Functionality

The primary function of this entity is to act as a container for powerful, randomly generated items. When the player interacts with the chest (indicated by `custom_pickup_string`), the associated Lua script (`data/scripts/items/chest_random_super.lua`) is triggered. This script is responsible for:

1.  **Opening the chest**: Visually and audibly indicating the chest has been opened.
2.  **Generating items**: Selecting and spawning one or more high-tier items within the chest's vicinity.

The `LightComponent` and `ParticleEmitterComponent` contribute to the visual feedback, making the chest appear special and rewarding when opened.