---
title: Darkness Chest Entity
category: biome
---

# Darkness Chest Entity

This document describes the `chest_darkness.xml` entity, which represents a special type of chest found in the game Noita. This chest is designed to be a static prop that can be interacted with, primarily for its loot.

## Key Components and Attributes

The `chest_darkness.xml` entity is composed of several key components that define its behavior and appearance.

### Entity Tags

The entity has the following tags, which influence its interactions and properties:

*   `teleportable_NOT`: Indicates that this entity cannot be teleported.
*   `item_physics`: Suggests it interacts with the game's physics system as an item.
*   `chest`: Identifies it as a chest.
*   `item_pickup`: Implies it can be picked up or interacted with for items.
*   `effectable_prop`: Means it can be affected by various game effects.

### UIInfoComponent

This component defines the user interface information for the chest.

*   `name`: `$item_chest_treasure` - This is a localization key, meaning the actual name displayed in-game will be retrieved from the game's localization files.

### PositionSeedComponent

This component is used to generate a unique position for the entity, ensuring variation in placement.

### PhysicsBodyComponent

This component defines the physical properties of the chest.

*   `uid`: `1` - A unique identifier for this physics body.
*   `allow_sleep`: `1` - The physics body can enter a sleep state when not in motion to save performance.
*   `fixed_rotation`: `0` - The chest can rotate.
*   `is_bullet`: `1` - Treated as a projectile-like object in physics simulations.
*   `auto_clean`: `1` - The physics body will be automatically cleaned up when no longer needed.
*   `hax_fix_going_through_ground`: `1` - A specific fix to prevent it from clipping through the ground.

### PhysicsImageShapeComponent

This component defines the visual shape and material of the chest based on an image.

*   `image_file`: `data/buildings_gfx/chest_random.png` - The sprite used for the chest's visual representation.
*   `material`: `wood_prop` - The in-game material assigned to this physics shape, which can affect interactions.

### ItemComponent

This component marks the entity as an item and defines its pickup behavior.

*   `item_name`: `$item_chest_treasure` - Similar to `UIInfoComponent`, this is a localization key for the item's name.
*   `custom_pickup_string`: `$itempickup_open` - The text displayed when the player interacts with the chest to open it.
*   `stats_count_as_item_pick_up`: `0` - This chest does not count towards the player's item pickup statistics.
*   `play_pick_sound`: `0` - No specific sound is played when the item is picked up (likely handled by Lua).

### LuaComponent

This is a crucial component that enables custom scripting for the chest.

*   `script_item_picked_up`: `data/biome_impl/static_tile/chest_darkness.lua` - The Lua script executed when the item is picked up. This script likely handles opening the chest and spawning its contents.
*   `script_physics_body_modified`: `data/biome_impl/static_tile/chest_darkness.lua` - The Lua script executed when the physics body of the chest is modified.
*   `execute_times`: `1` - The scripts associated with this component will execute only once.

### LightComponent

This component adds a light source to the chest.

*   `r`, `g`, `b`: `255`, `255`, `255` - Sets the light color to white.
*   `radius`: `64` - The range of the light emitted by the chest.
*   `fade_out_time`: `0.75` - The time it takes for the light to fade out.

## Associated Lua Script

The `LuaComponent` points to `data/biome_impl/static_tile/chest_darkness.lua`. This script is responsible for the chest's dynamic behavior, such as:

*   Opening the chest upon interaction.
*   Spawning the loot contained within the chest.
*   Potentially handling any visual or auditory effects associated with opening.

**Note:** The exact contents and functionality of the Lua script are not detailed in this XML file but are essential for understanding the full behavior of the darkness chest.