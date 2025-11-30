---
title: PositionSeedComponent
source: https://noita.wiki.gg/wiki/Documentation:PositionSeedComponent
category: modding-wiki
---

# PositionSeedComponent

This documentation page explains the `PositionSeedComponent` in Noita, a crucial component for managing and influencing the procedural generation of world elements. Understanding this component is vital for modders who wish to control the placement and behavior of entities, ensuring consistent and predictable outcomes in their custom content.

## Overview

The `PositionSeedComponent` is a fundamental entity component in Noita that dictates how an entity's position is influenced by the game's procedural generation seed. By attaching this component and configuring its parameters, modders can ensure that an entity's placement is deterministic and reproducible across different game sessions, provided the same seed is used. This is particularly useful for creating custom biomes, unique structures, or specific entity arrangements that should always appear in the same location relative to the world's seed.

## Component Parameters

The `PositionSeedComponent` has several parameters that can be adjusted to control its behavior. These parameters are typically defined within an entity's XML definition.

### `seed_offset_x` and `seed_offset_y`

These parameters define an offset that is added to the entity's position based on the world seed. This allows for fine-tuning the position relative to the seed's inherent generation.

*   **Type:** `float`
*   **Description:** A floating-point value representing the offset in the X and Y directions, respectively.

### `seed_scale_x` and `seed_scale_y`

These parameters control how much the world seed influences the entity's position. A scale of 1.0 means the seed has a direct influence, while a scale of 0.0 means the seed has no influence.

*   **Type:** `float`
*   **Description:** A floating-point value representing the scaling factor of the seed's influence on the X and Y positions.

### `seed_randomness_x` and `seed_randomness_y`

These parameters introduce a degree of randomness to the entity's position, still derived from the world seed. This allows for variations in placement while maintaining a degree of predictability.

*   **Type:** `float`
*   **Description:** A floating-point value representing the amount of randomness to apply to the X and Y positions, derived from the seed.

### `seed_use_entity_position`

This boolean parameter determines whether the entity's current position should be used as a base for the seed-based positioning.

*   **Type:** `bool`
*   **Description:** If `true`, the entity's existing position is used as a starting point for seed-based adjustments. If `false`, the position is generated entirely based on the seed and other parameters.

## Example Usage

Here's an example of how `PositionSeedComponent` might be used in an entity's XML definition:

```xml
<entity name="my_custom_object" >
    <PositionSeedComponent
        seed_offset_x="10.5"
        seed_offset_y="-5.2"
        seed_scale_x="0.8"
        seed_scale_y="1.2"
        seed_randomness_x="0.1"
        seed_randomness_y="0.15"
        seed_use_entity_position="true"
    />
    <!-- Other components -->
</entity>
```

In this example:
*   The entity's position will be offset by `10.5` in the X direction and `-5.2` in the Y direction, relative to the world seed.
*   The seed's influence on the X position is scaled by `0.8`, and on the Y position by `1.2`.
*   A small amount of seed-derived randomness (`0.1` for X, `0.15` for Y) is added to the position.
*   The entity's current defined position in the XML will serve as the base for these seed-based modifications.

## Implications for Modding

*   **Deterministic Placement:** By using `PositionSeedComponent`, modders can ensure that custom entities or structures appear in the same location every time a game is played with the same world seed. This is crucial for creating reproducible challenges, puzzles, or environmental storytelling.
*   **Controlled Randomness:** The `seed_randomness` parameters allow for variations in placement that still feel natural and tied to the world's generation, rather than purely arbitrary random placement.
*   **Biome and Structure Design:** This component is invaluable for designing custom biomes or unique structures that need to be placed consistently within specific areas of the world.
*   **Debugging:** Understanding how `PositionSeedComponent` works can aid in debugging issues related to entity placement in modded games.

## Related Components and Concepts

*   **Entity Components:** `PositionSeedComponent` is one of many components that can be attached to entities to define their behavior and properties.
*   **Procedural Generation:** The component is intrinsically linked to Noita's procedural generation system, which uses seeds to create unique game worlds.
*   **XML Entity Definitions:** All component configurations are defined within XML files that describe entities.

For more information on entity components and XML modding, refer to the [Modding:Entity Components](https://noita.wiki.gg/wiki/Modding:_Entity_Components) and [Modding:XML](https://noita.wiki.gg/wiki/Modding:_XML) pages.