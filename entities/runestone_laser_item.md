---
title: Runestone Laser Item
category: entities
---

# Runestone Laser Item

This document details the `runestone_laser.xml` entity, which defines the Laser Runestone pickup item in Noita.

## Core Components

The Runestone Laser inherits its base functionality from `runestone_base.xml`. Key components specific to this item are:

### PhysicsImageShapeComponent

Defines the visual representation of the runestone when it's in the game world.

*   `image_file`: `data/items_gfx/runestones/runestone_laser.png` - The sprite used for the runestone's physical form.

### ItemComponent

Manages the item's properties for inventory and UI.

*   `item_name`: `$item_runestone_laser` - The internal name for the item.
*   `ui_sprite`: `data/ui_gfx/items/runestone_laser.png` - The sprite displayed in the UI.
*   `ui_description`: `$itemdesc_runestone` - The description text key for the item.

### UIInfoComponent

Provides information for UI elements.

*   `name`: `$item_runestone_laser` - Links to the item's name for UI display.

### AbilityComponent

Associates the item with an ability.

*   `ui_name`: `$item_runestone_laser` - The name displayed for the ability in the UI.

### SpriteComponent

Defines the sprite when the item is held by the player.

*   `image_file`: `data/items_gfx/in_hand/runestone_laser.png` - The sprite used when the runestone is in the player's hand.

### ParticleEmitterComponent

Responsible for visual effects when the runestone is activated.

*   `_tags`: `"activate"` - This particle effect is triggered when the runestone is activated.
*   `_enabled`: `"0"` - Disabled by default, activated by game logic.
*   `emitted_material_name`: `"spark_green"` - The material used for the emitted sparks.
*   `lifetime_min`/`lifetime_max`: `8.01`/`8.1` - Duration of the particle effect.
*   `count_min`/`count_max`: `100`/`100` - Number of particles emitted.
*   `area_circle_radius.min`/`max`: `16`/`16` - The radius of the emission area.
*   `cosmetic_force_create`: `"1"` - Ensures particles are created even if not strictly necessary for gameplay.
*   `velocity_always_away_from_center`: `"100"` - Particles are pushed outwards from the center of emission.

### LuaComponent (Scripting)

This component links the runestone to its specific behavior script.

*   `_tags`: `"activate"` - This script is executed upon activation.
*   `script_source_file`: `data/scripts/items/runestones/runestone_laser.lua` - The Lua script that defines the runestone's functionality.
*   `execute_every_n_frame`: `"5"` - The script logic runs every 5 frames.
*   `_enabled`: `"0"` - Disabled by default, activated by game logic.