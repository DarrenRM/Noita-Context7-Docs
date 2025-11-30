---
title: Base Forged Tablet Item
category: entities
---

# Base Forged Tablet Item

This document details the `base_forged.xml` entity, which serves as a foundational template for forged tablet items in Noita. It defines the core properties and behaviors of these items when they exist in the game world and when held by the player.

## Core Components

The `base_forged.xml` entity is constructed using several key components that dictate its functionality:

### `BookComponent`

*   **Purpose:** Marks this entity as a book item. This is a fundamental tag for identifying and interacting with books within the game.

### `UIInfoComponent`

*   **`name`**: `$booktitle01`
    *   **Description:** A localization key that defines the in-game name of the item. This allows for easy translation and management of item names.

### `PhysicsBodyComponent`

*   **Purpose:** Defines the physical properties of the item in the game world.
*   **Key Attributes:**
    *   `allow_sleep`: `1` - Allows the physics body to enter a sleep state when inactive to save performance.
    *   `auto_clean`: `1` - Automatically cleans up the physics body when it's no longer needed.
    *   `hax_fix_going_through_ground`: `1` - A workaround to prevent the item from falling through the ground.

### `PhysicsImageShapeComponent`

*   **Purpose:** Defines the visual shape and collision properties of the item based on an image.
*   **Key Attributes:**
    *   `image_file`: `data/items_gfx/laboratory_tablet.png` - The sprite used for the item's visual representation in the world.
    *   `material`: `rock_box2d_hard` - The physics material defining its hardness and interaction properties.

### `PhysicsThrowableComponent`

*   **Purpose:** Enables the item to be thrown by the player.
*   **Key Attributes:**
    *   `max_throw_speed`: `130` - The maximum speed the item can be thrown.
    *   `throw_force_coeff`: `1.5` - A coefficient that influences the force applied when throwing.

### `ProjectileComponent`

*   **Purpose:** Defines projectile-like behavior when the item is thrown.
*   **Key Attributes:**
    *   `lifetime`: `-1` - The projectile will not despawn on its own.
    *   `penetrate_entities`: `1` - Allows the projectile to pass through other entities.
    *   `never_hit_player`: `1` - Ensures the thrown item never harms the player.

### `ItemComponent`

*   **Purpose:** Defines the item's properties for inventory and player interaction.
*   **Key Attributes:**
    *   `is_pickable`: `1` - Allows the player to pick up the item.
    *   `is_equipable_forced`: `1` - Indicates the item can be equipped.
    *   `ui_sprite`: `data/ui_gfx/items/laboratory_tablet.png` - The sprite used for the item in the UI and inventory.
    *   `item_name`: `$booktitle01` - The localization key for the item's name.
    *   `ui_description`: `$bookdesc01` - The localization key for the item's description.

### `SpriteComponent`

*   **Purpose:** Defines the visual representation of the item when held in the player's hand.
*   **Key Attributes:**
    *   `image_file`: `data/items_gfx/in_hand/laboratory_tablet_in_hand.png` - The sprite for the item when equipped.
    *   `_enabled`: `0` - This sprite is initially disabled, likely to be enabled by other game logic when the item is held.

### `HitboxComponent`

*   **Purpose:** Defines the collision area of the item in the game world.
*   **Key Attributes:**
    *   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Define the bounding box for physics interactions.

### `LightComponent`

*   **Purpose:** Adds a light source to the item.
*   **Key Attributes:**
    *   `r`, `g`, `b`: `255` - Sets the light color to white.
    *   `radius`: `64` - The range of the light.
    *   `fade_out_time`: `0.75` - How long it takes for the light to fade out.

### `ParticleEmitterComponent`

*   **Purpose:** Creates cosmetic particles around the item, enhancing its visual appeal.
*   **Key Attributes:**
    *   `emitted_material_name`: `spark_white` - The type of particle to emit.
    *   `count_min`/`count_max`: `1` - The number of particles emitted per emission.
    *   `emission_interval_min_frames`/`emission_interval_max_frames`: Controls the frequency of particle emissions.
    *   `area_circle_radius.max`: `6` - The radius of the area where particles can be emitted.
    *   `lifetime_min`/`lifetime_max`: `2.5`/`6.5` - The duration particles exist.
    *   `gravity.y`: `0.0` - Particles are not affected by gravity.

### `AbilityComponent`

*   **Purpose:** Grants the item specific abilities, in this case, the ability to be thrown as an item.
*   **Key Attributes:**
    *   `ui_name`: `$booktitle01` - The name displayed for the ability in the UI.
    *   `throw_as_item`: `1` - Enables the item to be thrown.
    *   `gun_config`:
        *   `deck_capacity`: `0` - Indicates this item does not have a spell deck capacity.

This `base_forged.xml` entity provides a robust foundation for creating various forged tablet items by defining their visual appearance, physical behavior, interaction capabilities, and cosmetic effects. Modders can extend this by adding specific spell data or modifying existing attributes.