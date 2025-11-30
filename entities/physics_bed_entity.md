---
title: Physics Bed Entity
category: entities
---

# Physics Bed Entity

This document describes the `physics_bed.xml` entity, a prop designed for use in Noita. It's a physics-enabled object with specific damage and visual properties.

## Key Components

### Base Entity

The entity inherits its core functionality from `base_item_physics.xml`.

### Physics Image Shape Component

This component defines the visual representation and physical properties of the bed.

*   **`image_file`**: `data/props_gfx/bed.png` - Specifies the texture used for the bed.
*   **`material`**: `wood_prop` - Defines the physical material properties, influencing interactions.
*   **`centered`**: `1` - Indicates the image is centered on its physics body.

### Camera Bound Component

This component manages how the entity interacts with the camera's view.

*   **`max_count`**: `50` - The maximum number of these entities that can be active within the camera's view.
*   **`distance`**: `500` - The maximum distance from the camera at which this entity will be processed.

### Damage Model Component

This component defines how the bed takes damage and its behavior when damaged.

*   **`hp`**: `800` - The total hit points of the bed.
*   **`falling_damages`**: `1` - Enables falling damage for the entity.
*   **`falling_damage_damage_min`**: `0.1` - The minimum damage taken from falling.
*   **`falling_damage_damage_max`**: `1.2` - The maximum damage taken from falling.
*   **`falling_damage_height_min`**: `70` - The minimum height from which falling damage is applied.
*   **`falling_damage_height_max`**: `250` - The maximum height from which falling damage is applied.
*   **`fire_damage_amount`**: `0.2` - The amount of damage taken from fire per tick.
*   **`air_needed`**: `0` - The entity does not require air to survive.
*   **`drop_items_on_death`**: `0` - No items are dropped when the entity is destroyed.
*   **`ui_report_damage`**: `0` - Damage taken by this entity is not reported in the UI.
*   **`critical_damage_resistance`**: `1` - The entity has no resistance to critical damage.