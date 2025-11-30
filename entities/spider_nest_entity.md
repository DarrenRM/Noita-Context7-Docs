---
title: Spider Nest Entity
category: entities
---

# Spider Nest Entity

This document describes the `spidernest.xml` entity, which represents a spider nest in Noita. It details its core attributes related to damage, AI behavior, collision, and visual representation.

## Core Attributes

The `Entity` tag defines the fundamental properties of the spider nest.

*   **name**: `unknown` (This is a placeholder and might be intended to be more specific).
*   **tags**: `mortal`, `nest`, `predator`, `hittable`, `glue_NOT`. These tags define its behavior and interactions within the game world.

## DamageModelComponent

This component governs how the spider nest takes damage and its resistance to various elements.

*   **hp**: `5` - The current health points of the nest.
*   **max\_hp**: `5` - The maximum health points the nest can have.
*   **fire\_damage\_amount**: `0.2` - The amount of damage taken from fire per tick.
*   **fire\_probability\_of\_ignition**: `0.5` - The chance for the nest to catch fire.
*   **materials\_that\_damage**: `acid,lava,poison,blood_cold,blood_cold_vapour` - A list of materials that inflict damage upon contact.
*   **materials\_how\_much\_damage**: `0.004,0.004,0.001,0.0008,0.0007` - The corresponding damage values for each material listed in `materials_that_damage`.
*   **falling\_damage\_damage\_max**: `1.2` - The maximum damage dealt by falling.
*   **falling\_damage\_height\_min**: `70` - The minimum height required to start taking falling damage.
*   **drop\_items\_on\_death**: `1` - Indicates that items will be dropped when the nest is destroyed.

## GenomeDataComponent

This component defines the nest's role within the game's ecosystem and AI.

*   **food\_chain\_rank**: `20` - A numerical value representing its position in the food chain. Higher numbers generally indicate a higher rank.
*   **herd\_id**: `nest` - Identifies this entity as belonging to a "nest" group, likely for AI pathfinding or behavior.
*   **is\_predator**: `1` - Marks the nest as a predator, influencing its AI interactions.

## HitboxComponent

Defines the collision boundaries of the spider nest.

*   **aabb\_max\_x**: `10.7143`
*   **aabb\_max\_y**: `-12.71429`
*   **aabb\_min\_x**: `-9.42857`
*   **aabb\_min\_y**: `-30`
    These values define the axis-aligned bounding box (AABB) for collision detection.
*   **is\_enemy**: `0` - Not considered an enemy by default.
*   **is\_item**: `0` - Not treated as a collectible item.
*   **is\_player**: `0` - Not a player character.

## LuaComponent

This component links the entity to a Lua script for custom behavior.

*   **script\_source\_file**: `data/scripts/buildings/spidernest.lua` - The path to the Lua script that controls the nest's dynamic behavior.
*   **execute\_every\_n\_frame**: `101` - The script logic will execute every 101 frames.
*   **execute\_times**: `-1` - The script will execute indefinitely.

## SpriteComponent

Manages the visual representation of the spider nest.

*   **image\_file**: `data/buildings_gfx/spidernest.xml` - Specifies the graphical asset used for the nest.
*   **offset\_x**: `0`
*   **offset\_y**: `0` - These control the sprite's position relative to the entity's origin.
*   **alpha**: `1` - The opacity of the sprite (fully opaque).
*   **visible**: `1` - The sprite is visible.

## ItemChestComponent

This component indicates that the spider nest can contain items, acting as a loot container.

*   **item\_count\_min**: `3` - The minimum number of items that can be found inside.
*   **item\_count\_max**: `4` - The maximum number of items that can be found inside.
*   **level**: `3` - The loot level, which influences the quality and type of items found.