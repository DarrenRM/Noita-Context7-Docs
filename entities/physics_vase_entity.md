---
title: Physics Vase Entity
category: entities
---

# Physics Vase Entity

This document describes the `physics_vase.xml` entity, a breakable prop in Noita that contains and spills materials when damaged or destroyed.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits fundamental physics and item properties.

### Physics Image Shape Component

*   **`image_file="data/props_gfx/vase.png"`**: Specifies the visual sprite for the vase.
*   **`material="rock_box2d"`**: Defines the physics material, influencing its interaction with the game world (e.g., friction, density).

### Camera Bound Component

*   **`max_count="50"`**: Limits the number of these entities that can be active within the camera's view.
*   **`distance="500"`**: Sets the maximum distance from the camera at which the entity will be rendered and simulated.

### Material Inventory Component

This component manages the materials contained within the vase.

*   **`_enabled="1"`**: Ensures the component is active.
*   **`drop_as_item="0"`**: The vase itself does not drop as a collectible item upon death.
*   **`on_death_spill="1"`**: When destroyed, the contained materials will spill out.
*   **`leak_on_damage_percent="0.8"`**: If the vase takes damage exceeding 80% of its HP, it will start leaking its contents.

#### `count_per_material_type`

Defines the types and quantities of materials stored within the vase.

| Material           | Count |
| :----------------- | :---- |
| `gunpowder_unstable` | 150   |

### Damage Model Component

Manages the vase's health, damage resistances, and how it reacts to damage.

*   **`hp="5"`**: The vase has 5 hit points.
*   **`falling_damage_damage_max="1.2"`**: Maximum damage dealt by falling.
*   **`falling_damage_damage_min="0.1"`**: Minimum damage dealt by falling.
*   **`falling_damage_height_max="250"`**: Maximum height from which falling damage is calculated.
*   **`falling_damage_height_min="70"`**: Minimum height from which falling damage is calculated.
*   **`falling_damages="1"`**: Enables falling damage for this entity.
*   **`fire_damage_amount="0.2"`**: Amount of damage taken from fire per tick.
*   **`fire_probability_of_ignition="10"`**: 10% chance to ignite when exposed to fire.
*   **`critical_damage_resistance="1"`**: The vase has no resistance to critical damage.
*   **`air_needed="0"`**: Does not require air to function.
*   **`blood_material="sand_blue"`**: If the vase were to bleed (not applicable here, but a general property), it would use `sand_blue`.
*   **`drop_items_on_death="0"`**: Does not drop any specific items upon death, beyond its contained materials.
*   **`materials_create_messages="0"`**: Does not generate messages when materials interact with it.
*   **`materials_damage="0"`**: Materials do not directly damage the vase.
*   **`ragdoll_filenames_file=""`**: No specific ragdoll files are used.
*   **`ragdoll_material=""`**: No specific ragdoll material is used.
*   **`ui_report_damage="0"`**: Damage taken by the vase is not reported in the UI.