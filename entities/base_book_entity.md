---
title: Base Book Entity
category: entities
---

---

# Base Book Entity

This document describes the base entity for books in Noita, serving as a foundational template for various magical tomes.

## Core Components

The `base_book.xml` entity utilizes several key components to define its behavior and appearance.

### `BookComponent`

This component signifies that the entity is a book. It's a simple marker and doesn't contain specific attributes in this base version.

### `UIInfoComponent`

Defines the user interface information for the book.

*   **`name`**: `$booktitle01` - A localization key for the book's title.

### `ItemComponent`

Handles the item-specific properties, making the book interactable within the game's inventory and world.

*   **`is_pickable`**: `1` - Allows the player to pick up the book.
*   **`is_equipable_forced`**: `1` - Indicates the book can be equipped.
*   **`ui_sprite`**: `data/ui_gfx/items/emerald_tablet.png` - The sprite displayed in the UI.
*   **`preferred_inventory`**: `QUICK` - Suggests the book should be placed in the quick inventory.
*   **`item_name`**: `$booktitle01` - The internal name for the item, often linked to localization.
*   **`ui_description`**: `$bookdesc01` - A localization key for the book's description.

### `PhysicsBodyComponent`

Manages the physical properties of the book in the game world.

*   **`allow_sleep`**: `1` - Allows the physics body to sleep when not in motion to save performance.
*   **`is_bullet`**: `1` - Treats the entity as a bullet for physics interactions.
*   **`auto_clean`**: `1` - Automatically cleans up the physics body when no longer needed.
*   **`hax_fix_going_through_ground`**: `1` - A fix to prevent the entity from clipping through the ground.

### `PhysicsImageShapeComponent`

Defines the visual shape and material of the book for physics interactions.

*   **`image_file`**: `data/items_gfx/emerald_tablet.png` - The image used for the physics shape.
*   **`material`**: `rock_box2d_hard` - The physics material, influencing how it interacts with other objects.

### `PhysicsThrowableComponent`

Enables the book to be thrown.

*   **`max_throw_speed`**: `130` - The maximum speed the book can be thrown.
*   **`throw_force_coeff`**: `1.5` - A coefficient affecting the force applied when throwing.

### `ProjectileComponent`

Configures the entity as a projectile, though in this context, it's more about its interaction when thrown.

*   **`lifetime`**: `-1` - Indicates the projectile does not have a limited lifetime.
*   **`penetrate_entities`**: `1` - Allows the projectile to pass through other entities.
*   **`never_hit_player`**: `1` - Prevents the projectile from hitting the player.

### `SpriteComponent`

Defines the visual representation of the book when held in hand.

*   **`image_file`**: `data/items_gfx/in_hand/emerald_tablet_in_hand.png` - The sprite for when the book is in the player's hand.
*   **`_enabled`**: `0` - This sprite is initially disabled, suggesting it's only shown when the book is equipped.

### `HitboxComponent`

Defines the collision area of the book.

*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: Define the bounding box for collision detection.

### `LightComponent`

Adds a light source to the book.

*   **`r`, `g`, `b`**: `255` - Sets the light color to white.
*   **`radius`**: `64` - The radius of the light emitted.
*   **`fade_out_time`**: `0.75` - How long it takes for the light to fade out.

### `ParticleEmitterComponent`

Responsible for emitting cosmetic particles, often for visual flair.

*   **`emitted_material_name`**: `spark_green` - The material of the particles to be emitted.
*   **`count_min`, `count_max`**: `1` - Emits a single particle per emission.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1` to `3` - Controls the frequency of particle emissions.
*   **`lifetime_min`, `lifetime_max`**: `2.5` to `6.5` - The duration particles exist.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.

### `AbilityComponent`

Grants the entity abilities, in this case, the ability to be thrown as an item.

*   **`throw_as_item`**: `1` - Enables the throwing functionality.
*   **`gun_config`**:
    *   **`deck_capacity`**: `0` - Indicates no spell deck capacity, as it's not a spellcasting book in this base form.