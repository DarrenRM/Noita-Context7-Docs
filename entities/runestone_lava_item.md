---
title: Runestone Lava Item
category: entities
---

# Runestone Lava Item

This document details the `runestone_lava.xml` entity, which defines the Lava Runestone item in Noita. This runestone grants the player the ability to cast lava-related spells.

## Key Components

### Base Entity

The runestone inherits its base properties from `data/entities/items/pickup/runestones/runestone_base.xml`.

### Physics Image Shape Component

Defines the visual representation of the runestone when it's an item pickup in the game world.

*   `image_file`: `data/items_gfx/runestones/runestone_lava.png` - Specifies the sprite for the runestone pickup.

### Item Component

Configures the item's properties for inventory and UI.

*   `item_name`: `$item_runestone_lava` - The internal name for the item.
*   `ui_sprite`: `data/ui_gfx/items/runestone_lava.png` - The sprite displayed in the UI.
*   `ui_description`: `$itemdesc_runestone` - The description text for the item.

### UI Info Component

Provides information for the UI.

*   `name`: `$item_runestone_lava` - Links to the item's name for UI display.

### Ability Component

Defines the abilities associated with the runestone.

*   `ui_name`: `$item_runestone_lava` - The name displayed in the UI for the ability.

### Sprite Component

Defines the visual representation of the runestone when held by the player.

*   `image_file`: `data/items_gfx/in_hand/runestone_lava.png` - The sprite for the runestone when in the player's hand.

### Particle Emitter Component

Responsible for generating visual effects when the runestone is activated.

*   `emitted_material_name`: `spark_red` - The material used for the emitted particles.
*   `lifetime_min`/`lifetime_max`: `10.01` - Duration of particle emission.
*   `count_min`/`count_max`: `200` - Number of particles emitted.
*   `area_circle_radius.min`/`area_circle_radius.max`: `16` - The radius of the area from which particles are emitted.
*   `cosmetic_force_create`: `1` - Ensures particles are created cosmetically.
*   `airflow_force`: `0.551` - Controls the force of airflow on particles.
*   `velocity_always_away_from_center`: `120` - Particles are always emitted away from the center.

### Lua Component (Script)

This component links to the Lua script that handles the runestone's functionality.

*   `script_source_file`: `data/scripts/items/runestones/runestone_lava.lua` - The path to the script that defines the runestone's behavior.
*   `execute_every_n_frame`: `40` - The script logic executes every 40 frames.