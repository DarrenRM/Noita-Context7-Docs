---
title: Area Damage Component
category: entities
---

# Area Damage Component

This component defines an area that deals damage to entities within its bounds. It's a fundamental building block for various damaging effects in Noita.

## Key Attributes

The `AreaDamageComponent` is relatively simple, with its primary function being to inflict damage.

*   **`damage`**: The amount of damage dealt by the area.
*   **`damage_type`**: The type of damage (e.g., `fire`, `explosion`, `physical`). This influences resistances and other damage interactions.
*   **`damage_ தடுப்பு`**: A boolean indicating whether damage should be blocked by certain materials or effects.
*   **`damage_radius`**: The radius of the circular area that deals damage.
*   **`damage_tick_delay`**: The time in seconds between damage ticks within the area.
*   **`damage_source_entity`**: The entity that is the source of this damage. This can be important for tracking damage origins and applying specific effects.
*   **`damage_to_player`**: A boolean indicating whether the player is affected by this damage.
*   **`damage_to_enemies`**: A boolean indicating whether enemies are affected by this damage.
*   **`damage_to_allies`**: A boolean indicating whether allies are affected by this damage.

## Usage Example

While the provided XML is minimal, a typical usage would involve placing this component within an entity that is intended to cause damage over time or as an instantaneous burst.

```xml
<Entity name="BurningArea">
    <AreaDamageComponent
        damage="5"
        damage_type="fire"
        damage_radius="50"
        damage_tick_delay="0.5"
        damage_to_player="true"
        damage_to_enemies="true"
        damage_to_allies="false"
    />
    <!-- Other components like Position, Sprite, etc. would be here -->
</Entity>
```