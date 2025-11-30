---
title: Orb 07 - Cloud Thunder
category: entities
---

# Orb 07 - Cloud Thunder

This entity defines the "Cloud Thunder" orb, a special item in Noita. It inherits its base properties from `orb_base.xml` and `orb_particles_base.xml`, with specific configurations for its appearance and behavior.

## Key Attributes

| Attribute           | Value                               | Description                                                                 |
| :------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `orb_id`            | 7                                   | Unique identifier for this orb type.                                        |
| `image_file`        | `data/items_gfx/orbs/orb_07.xml`    | Specifies the graphical asset used for the orb's sprite.                    |
| `card_name`         | `CLOUD_THUNDER`                     | The internal name or identifier for the card associated with this orb.      |
| `script_item_picked_up` | `data/scripts/items/orb_07_trap.lua` | The Lua script executed when the orb is picked up, likely triggering its effect. |

## Inheritance

*   **`data/entities/items/orbs/orb_base.xml`**: Provides fundamental orb properties and behaviors.
*   **`data/entities/items/orbs/orb_particles_base.xml`**: Defines particle effects associated with the orb.

## Transform Component

This section defines the relative positioning of the orb's visual elements.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `position.x`| 0     | X-axis offset from the parent entity.           |
| `position.y`| -11   | Y-axis offset from the parent entity (upwards). |

## Lua Component

The `LuaComponent` is crucial for defining the orb's unique functionality.

| Attribute           | Value                               | Description                                                                 |
| :------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `script_item_picked_up` | `data/scripts/items/orb_07_trap.lua` | This script is executed when the player picks up the orb, likely activating its "Cloud Thunder" effect. |