---
title: Runestone Fireball Item
category: entities
---

# Runestone Fireball Item

This document details the configuration for the "Runestone Fireball" item in Noita, focusing on its entity properties and how it functions within the game.

## Entity Definition

The Runestone Fireball is an item pickup that grants the player the Fireball spell. It inherits base properties from `runestone_base.xml`.

### Key Components and Attributes

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/items_gfx/runestones/runestone_fireball.png` - Defines the visual appearance of the runestone when it's in the game world.

*   **`ItemComponent`**:
    *   `item_name`: `$item_runestone_fireball` - The internal name for the item, used for referencing in game logic and localization.
    *   `ui_sprite`: `data/ui_gfx/items/runestone_fireball.png` - The sprite used to represent this item in the player's inventory and UI.
    *   `ui_description`: `$itemdesc_runestone` - A localization key for the item's description text.

*   **`UIInfoComponent`**:
    *   `name`: `$item_runestone_fireball` - Similar to `item_name`, this is used for UI display.

*   **`AbilityComponent`**:
    *   `ui_name`: `$item_runestone_fireball` - Used for displaying the item's name in UI elements related to abilities.

*   **`SpriteComponent`**:
    *   `image_file`: `data/items_gfx/in_hand/runestone_fireball.png` - The sprite used when the player is holding the runestone.

*   **`ParticleEmitterComponent`**:
    *   `_tags`: "activate" - This tag suggests the particle effect is triggered when the runestone is activated.
    *   `_enabled`: "0" - The particle emitter is initially disabled.
    *   `emitted_material_name`: "spark" - The type of material that will be emitted as particles.
    *   `lifetime_min`/`lifetime_max`: "8.01"/"8.1" - Controls the duration of the particle effect.
    *   `count_min`/`count_max`: "100"/"100" - The number of particles to emit.
    *   `area_circle_radius.min`/`max`: "16"/"16" - The radius of the area from which particles are emitted.
    *   `cosmetic_force_create`: "1" - Ensures particles are created even if other conditions aren't met.
    *   `velocity_always_away_from_center`: "100" - Particles are pushed outwards from the emission center.

*   **`LuaComponent` (Scripting)**:
    *   `_tags`: "activate" - Indicates this script is executed upon activation.
    *   `script_source_file`: `data/scripts/items/runestones/runestone_fireball.lua` - The primary script file that defines the runestone's behavior and grants the Fireball spell.
    *   `execute_every_n_frame`: "5" - The script logic will run every 5 frames.
    *   `_enabled`: "0" - The script is initially disabled.

### Summary of Functionality

The Runestone Fireball is a pickup item that, when activated, triggers a particle effect (sparks) and executes a Lua script. This script is responsible for granting the player the Fireball spell, likely by modifying the player's spell inventory or abilities. The visual assets define its appearance in the world, in hand, and in the UI.