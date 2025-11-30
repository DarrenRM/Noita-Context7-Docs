---
title: MagicXRayComponent
source: https://noita.wiki.gg/wiki/Documentation:MagicXRayComponent
category: modding-wiki
---

# MagicXRayComponent

This documentation page details the `MagicXRayComponent` in Noita, a crucial component for understanding and modifying how spells interact with the environment, particularly concerning their ability to reveal hidden elements. Modders can leverage this information to create new spell effects, alter existing ones, or implement unique gameplay mechanics related to vision and detection.

## Overview

The `MagicXRayComponent` is a fundamental part of Noita's spell system, controlling the "x-ray" or "reveal" properties of certain magical effects. This component dictates what types of entities or terrain the spell can detect and how that information is presented to the player. Understanding its parameters is key to creating spells that can, for example, highlight enemies through walls, reveal hidden items, or even alter the visual properties of the game world.

## Component Parameters

The `MagicXRayComponent` has several parameters that can be configured within the spell's XML definition. These parameters allow for fine-grained control over the x-ray effect.

### `xray_material_tag`

This parameter specifies a material tag that the x-ray effect will target. When a spell with this component hits an entity or terrain with a matching material tag, it will be revealed.

*   **Type:** String
*   **Description:** The material tag to search for.

### `xray_entity_tag`

Similar to `xray_material_tag`, this parameter targets specific entity tags. Spells can be configured to reveal entities that possess a particular tag.

*   **Type:** String
*   **Description:** The entity tag to search for.

### `xray_biome_tag`

This parameter allows the x-ray effect to target specific biomes. This can be used to create spells that only reveal certain types of terrain or areas.

*   **Type:** String
*   **Description:** The biome tag to search for.

### `xray_radius`

Defines the radius around the point of impact or the spell's origin within which the x-ray effect will search for targets.

*   **Type:** Float
*   **Description:** The radius of the x-ray detection.

### `xray_duration`

Sets the duration for which the x-ray effect will persist after being triggered.

*   **Type:** Float
*   **Description:** The duration of the x-ray effect in seconds.

### `xray_color`

Specifies the color used to highlight the revealed entities or terrain. This is often an RGBA value.

*   **Type:** String (RGBA format, e.g., "255,0,0,255" for red)
*   **Description:** The color to use for highlighting.

### `xray_visual_effect`

Allows for the attachment of a specific visual effect (e.g., a particle effect) to the revealed entities or terrain.

*   **Type:** String (Name of the visual effect prefab)
*   **Description:** The visual effect to apply.

### `xray_sound_effect`

Enables the playback of a sound effect when the x-ray effect is triggered.

*   **Type:** String (Name of the sound effect)
*   **Description:** The sound effect to play.

## Example Usage

Here's an example of how `MagicXRayComponent` might be used in a spell's XML definition. This spell would reveal enemies within a certain radius for a short duration with a red highlight.

```xml
<spell name="Reveal Enemies">
    <property name="description" value="Reveals nearby enemies." />
    <property name="material_type" value="magic" />
    <property name="spell_type" value="projectile" />
    <property name="target_type" value="enemy" />
    <property name="damage" value="0" />
    <property name="mana_cost" value="10" />
    <property name="speed" value="30" />
    <property name="lifetime" value="2" />
    <property name="projectile_file" value="data/projectiles/generic_projectile.xml" />
    <component
        name="MagicXRayComponent"
        xray_entity_tag="enemy"
        xray_radius="100"
        xray_duration="5"
        xray_color="255,0,0,255"
        xray_visual_effect="effects/xray_highlight.xml"
        xray_sound_effect="sounds/xray_reveal.ogg"
        />
</spell>
```

## Related Components and Concepts

*   **`MagicComponent`**: The base component for most magical effects, often used in conjunction with `MagicXRayComponent`.
*   **Material Tags**: Used to categorize different types of terrain and objects.
*   **Entity Tags**: Used to categorize different types of entities (enemies, items, etc.).
*   **Biome Tags**: Used to categorize different areas of the game world.
*   **Lua API**: For more advanced control and dynamic effects, the Lua API can be used to interact with and modify spell components. You can find more information on the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).

## Further Modding Resources

*   [Noita Modding Wiki](https://noita.wiki.gg/wiki/Modding)
*   [Spell Modding Guide](https://noita.wiki.gg/wiki/Modding:_Spell_Modding)