---
title: HealthBarComponent
source: https://noita.wiki.gg/wiki/Documentation:HealthBarComponent
category: modding-wiki
---

# HealthBarComponent

This documentation covers the `HealthBarComponent` in Noita, a crucial component for managing and displaying health bars for entities. Understanding this component is essential for modders who wish to customize health display, create new entities with health mechanics, or modify existing ones.

## Overview

The `HealthBarComponent` is responsible for the visual representation of an entity's health. It dictates how the health bar appears, its color, and how it updates as the entity takes damage or heals. This component is typically attached to entities that have a health pool and require a visual indicator of their current health status.

## Component Properties

The `HealthBarComponent` has several properties that can be configured in the entity's XML definition. These properties allow for fine-grained control over the health bar's appearance and behavior.

### `health_bar_sprite_file`

*   **Type:** String
*   **Description:** Specifies the path to the sprite file used for the health bar. This sprite will be rendered to represent the health bar itself.

### `health_bar_sprite_file_empty`

*   **Type:** String
*   **Description:** Specifies the path to the sprite file used for the empty portion of the health bar. This is the part of the bar that is visible when the entity has taken damage.

### `health_bar_sprite_file_full`

*   **Type:** String
*   **Description:** Specifies the path to the sprite file used for the full portion of the health bar. This is the part of the bar that is visible when the entity is at full health.

### `health_bar_sprite_file_background`

*   **Type:** String
*   **Description:** Specifies the path to the sprite file used for the background of the health bar. This can be used to create a frame or container for the health bar.

### `health_bar_offset_x`

*   **Type:** Float
*   **Description:** The horizontal offset of the health bar from the entity's origin.

### `health_bar_offset_y`

*   **Type:** Float
*   **Description:** The vertical offset of the health bar from the entity's origin.

### `health_bar_scale_x`

*   **Type:** Float
*   **Description:** The horizontal scaling factor for the health bar.

### `health_bar_scale_y`

*   **Type:** Float
*   **Description:** The vertical scaling factor for the health bar.

### `health_bar_always_visible`

*   **Type:** Boolean
*   **Description:** If `true`, the health bar will always be visible, regardless of the entity's health status. If `false`, it may only appear when the entity is damaged or in combat.

### `health_bar_hide_when_full`

*   **Type:** Boolean
*   **Description:** If `true`, the health bar will be hidden when the entity is at full health.

### `health_bar_hide_when_dead`

*   **Type:** Boolean
*   **Description:** If `true`, the health bar will be hidden when the entity is dead.

### `health_bar_color_r`

*   **Type:** Float
*   **Description:** The red component of the health bar's color (0.0 to 1.0).

### `health_bar_color_g`

*   **Type:** Float
*   **Description:** The green component of the health bar's color (0.0 to 1.0).

### `health_bar_color_b`

*   **Type:** Float
*   **Description:** The blue component of the health bar's color (0.0 to 1.0).

### `health_bar_color_a`

*   **Type:** Float
*   **Description:** The alpha (transparency) component of the health bar's color (0.0 to 1.0).

### `health_bar_damage_flash_color_r`

*   **Type:** Float
*   **Description:** The red component of the flash color when the entity takes damage (0.0 to 1.0).

### `health_bar_damage_flash_color_g`

*   **Type:** Float
*   **Description:** The green component of the flash color when the entity takes damage (0.0 to 1.0).

### `health_bar_damage_flash_color_b`

*   **Type:** Float
*   **Description:** The blue component of the flash color when the entity takes damage (0.0 to 1.0).

### `health_bar_damage_flash_color_a`

*   **Type:** Float
*   **Description:** The alpha (transparency) component of the flash color when the entity takes damage (0.0 to 1.0).

### `health_bar_damage_flash_duration`

*   **Type:** Float
*   **Description:** The duration of the damage flash effect in seconds.

### `health_bar_damage_flash_fade_out_duration`

*   **Type:** Float
*   **Description:** The duration of the fade-out for the damage flash effect in seconds.

### `health_bar_damage_flash_fade_in_duration`

*   **Type:** Float
*   **Description:** The duration of the fade-in for the damage flash effect in seconds.

### `health_bar_damage_flash_scale_x`

*   **Type:** Float
*   **Description:** The horizontal scaling factor for the damage flash effect.

### `health_bar_damage_flash_scale_y`

*   **Type:** Float
*   **Description:** The vertical scaling factor for the damage flash effect.

### `health_bar_damage_flash_offset_x`

*   **Type:** Float
*   **Description:** The horizontal offset of the damage flash effect from the health bar's origin.

### `health_bar_damage_flash_offset_y`

*   **Type:** Float
*   **Description:** The vertical offset of the damage flash effect from the health bar's origin.

### `health_bar_damage_flash_sprite_file`

*   **Type:** String
*   **Description:** Specifies the path to the sprite file used for the damage flash effect.

## Example XML Definition

Here's an example of how `HealthBarComponent` might be defined within an entity's XML file:

```xml
<Entity name="my_enemy_with_healthbar">
    <HealthComponent
        max_hp="100"
        hp="100"
    />
    <HealthBarComponent
        health_bar_sprite_file="data/sprites/ui/health_bar.png"
        health_bar_sprite_file_empty="data/sprites/ui/health_bar_empty.png"
        health_bar_sprite_file_full="data/sprites/ui/health_bar_full.png"
        health_bar_offset_x="0"
        health_bar_offset_y="20"
        health_bar_always_visible="true"
        health_bar_color_r="1.0"
        health_bar_color_g="0.0"
        health_bar_color_b="0.0"
        health_bar_color_a="1.0"
        health_bar_damage_flash_color_r="1.0"
        health_bar_damage_flash_color_g="0.5"
        health_bar_damage_flash_color_b="0.0"
        health_bar_damage_flash_color_a="1.0"
        health_bar_damage_flash_duration="0.2"
        health_bar_damage_flash_sprite_file="data/sprites/ui/health_bar_flash.png"
    />
    <!-- Other components -->
</Entity>
```

## Related Components and Concepts

*   **`HealthComponent`**: This component manages the actual health points (HP) of an entity. The `HealthBarComponent` typically visualizes the health managed by a `HealthComponent`.
*   **Entity XML Definitions**: Understanding how to define and modify entities in XML is fundamental to using components like `HealthBarComponent`. Refer to the [Modding:Entity XML](https://noita.wiki.gg/wiki/Modding:_Entity_XML) page for more details.
*   **Sprites**: The health bar's appearance is heavily reliant on sprite assets. Ensure you have appropriate sprite files or are referencing existing ones correctly.

## Further Modding Resources

*   [Modding:Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Modding:Entity XML](https://noita.wiki.gg/wiki/Modding:_Entity_XML)
*   [Modding:Components](https://noita.wiki.gg/wiki/Modding:_Components)