---
title: Orb of Destruction
category: entities
---

# Orb of Destruction

This entity defines the "Orb of Destruction" item in Noita. It inherits its base functionality from `orb_base.xml` and adds specific properties for its identity and visual representation.

## Key Attributes

*   **`orb_id`**: `13` - A unique identifier for this orb.
*   **`card_name`**: `"DESTRUCTION"` - The in-game name associated with this orb.
*   **`image_file`**: `"data/items_gfx/orbs/orb.xml"` - Specifies the graphical asset used for the orb's sprite.

## Components

### Base Entity

The orb inherits core properties from `data/entities/items/orbs/orb_base.xml`.

### Sprite Component

*   **`image_file`**: `"data/items_gfx/orbs/orb.xml"` - Defines the visual appearance of the orb.

### Variable Storage Component

*   **`name`**: `"card_name"`
*   **`value_string`**: `"DESTRUCTION"` - Stores the string identifier for the orb.

### Lua Component

*   **`_enabled`**: `0` - This component is currently disabled.

### Inherited Transform Component

This component is used to position the orb's associated particle effects.

*   **`position.x`**: `0`
*   **`position.y`**: `-11`

### Base Particle Component

The orb utilizes particle effects defined in `data/entities/items/orbs/orb_particles_base.xml`.