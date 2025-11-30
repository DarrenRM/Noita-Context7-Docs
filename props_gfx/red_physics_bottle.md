---
title: Red Physics Bottle
category: data/entities
---

# Red Physics Bottle

This document details the configuration of the `physics_bottle_red.xml` entity, a throwable prop in Noita that contains unstable gunpowder and explodes when damaged or destroyed.

## Base Entity Configuration

The entity inherits its core functionality from `base_item_physics2.xml`.

### Physics Body and Shape

*   **`kill_entity_after_initialized`**: Set to `0`, meaning the entity persists after its initial setup.
*   **`image_file`**: Specifies the visual representation of the bottle: `data/props_gfx/bottle_red.png`.
*   **`material`**: The physics material assigned is `plastic_prop`.

## Material Inventory Component

This component manages the contents of the bottle.

*   **`_enabled`**: Set to `1`, meaning the component is active.
*   **`drop_as_item`**: Set to `0`, indicating the contents do not drop as separate items upon destruction.
*   **`on_death_spill`**: Set to `1`, meaning the contents will spill out when the entity dies.
*   **`leak_on_damage_percent`**: Set to `0.999`, meaning the bottle will leak its contents when it reaches 99.9% damage.

### Contents

*   **`Material material="gunpowder_unstable" count="5"`**: The bottle contains 5 units of unstable gunpowder.

## Damage Model Component

This component defines how the entity reacts to damage.

*   **`air_needed`**: Set to `0`, indicating air is not required for its damage mechanics.
*   **`blood_material`**: Set to `alcohol`, though this seems to be a remnant and not directly applicable to gunpowder.
*   **`falling_damage_damage_max`**: Maximum damage from falling is `1.2`.
*   **`falling_damage_height_max`**: Maximum height for falling damage is `250`.
*   **`falling_damages`**: Set to `1`, enabling falling damage.
*   **`fire_damage_amount`**: Fire damage dealt is `0.2`.
*   **`fire_probability_of_ignition`**: `50`% chance of igniting from fire.
*   **`hp`**: The entity has very low health, `0.1`.
*   **`ui_report_damage`**: Set to `0`, so damage taken is not reported in the UI.

## Explode On Damage Component

This component governs the explosion behavior of the bottle.

*   **`explode_on_death_percent`**: Set to `1`, meaning it will always explode upon death.
*   **`explode_on_damage_percent`**: Set to `0.7`, meaning it will explode when it reaches 70% damage.
*   **`physics_body_modified_death_probability`**: `0.1` probability of exploding if the physics body is modified upon death.

### Explosion Configuration

*   **`damage`**: The explosion deals `1` damage.
*   **`camera_shake`**: `8` units of camera shake.
*   **`explosion_radius`**: The explosion has a radius of `10`.
*   **`explosion_sprite`**: Uses `data/particles/explosion_016.xml` for the explosion visual.
*   **`create_cell_material`**: The explosion creates `fire` cells.
*   **`hole_enabled`**: Set to `1`, creating holes in terrain.
*   **`ray_energy`**: The explosion has `80000` ray energy.
*   **`physics_explosion_power.min`**: Minimum physics explosion force is `0.08`.
*   **`physics_explosion_power.max`**: Maximum physics explosion force is `0.23`.
*   **`sparks_enabled`**: Set to `1`, generating sparks.
*   **`stains_enabled`**: Set to `1`, leaving stains.