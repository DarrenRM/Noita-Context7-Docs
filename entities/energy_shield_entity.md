---
title: Energy Shield Entity
category: entities
---

# Energy Shield Entity

This document describes the configuration for an energy shield entity in Noita, focusing on its core components and attributes relevant for AI-assisted modding.

## Entity Definition

The entity is defined with the tag `energy_shield`, indicating its primary function.

```xml
<Entity tags="energy_shield">
    <!-- Components go here -->
</Entity>
```

## Key Components and Attributes

### HitboxComponent

Defines the physical collision area of the shield.

| Attribute     | Value   | Description                                     |
| :------------ | :------ | :---------------------------------------------- |
| `aabb_min_x`  | `"-4"`  | Minimum X-axis bounding box coordinate.         |
| `aabb_max_x`  | `"4"`   | Maximum X-axis bounding box coordinate.         |
| `aabb_min_y`  | `"-3"`  | Minimum Y-axis bounding box coordinate.         |
| `aabb_max_y`  | `"3"`   | Maximum Y-axis bounding box coordinate.         |
| `_tags`       | `"enabled_in_world"` | Component is active when in the world. |

### InheritTransformComponent

Allows the shield to inherit the transform of its parent, typically the player's hand.

| Attribute     | Value   | Description                                     |
| :------------ | :------ | :---------------------------------------------- |
| `use_root_parent` | `"1"` | Inherits transform from the root parent.        |
| `_tags`       | `"enabled_in_hand"` | Component is active when held in hand. |

#### Transform

Specifies the relative position of the shield when inherited.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `position.x` | `"0"` | X-axis offset from the parent's origin.         |
| `position.y` | `"-4"` | Y-axis offset from the parent's origin.         |

### EnergyShieldComponent

The core component responsible for the shield's functionality.

| Attribute     | Value   | Description                                     |
| :------------ | :------ | :---------------------------------------------- |
| `recharge_speed` | `"0.22"` | How quickly the shield regenerates energy.      |
| `radius`      | `"10.0"` | The effective radius of the shield.             |
| `_tags`       | `"enabled_in_hand"` | Component is active when held in hand. |

### ParticleEmitterComponent (Multiple Instances)

These components control the visual effects of the shield, including ambient particles, a shield ring, and impact effects.

#### Ambient Particles (`shield_ring` tag)

*   **`emitted_material_name`**: `"plasma_fading"`
*   **`lifetime_min`**: `"0.02"`
*   **`lifetime_max`**: `"0.05"`
*   **`count_min`**: `"90"`
*   **`count_max`**: `"100"`
*   **`area_circle_radius.min`**: `"10"`
*   **`area_circle_radius.max`**: `"10"`
*   **`emission_interval_min_frames`**: `"0"`
*   **`emission_interval_max_frames`**: `"0"`
*   **`_tags`**: `"character,enabled_in_hand,shield_ring"`

#### Impact Particles (`shield_hit` tag)

*   **`emitted_material_name`**: `"plasma_fading"`
*   **`lifetime_min`**: `"0.3"`
*   **`lifetime_max`**: `"1"`
*   **`count_min`**: `"300"`
*   **`count_max`**: `"360"`
*   **`area_circle_radius.min`**: `"10"`
*   **`area_circle_radius.max`**: `"10"`
*   **`emission_interval_min_frames`**: `"0"`
*   **`emission_interval_max_frames`**: `"0"`
*   **`is_emitting`**: `"0"` (This suggests it's triggered by an event, not continuous)
*   **`_tags`**: `"character,enabled_in_hand,shield_hit"`

### LightComponent

Adds a light source to the shield.

| Attribute | Value   | Description                                     |
| :-------- | :------ | :---------------------------------------------- |
| `radius`  | `"60"`  | The radius of the light effect.                 |
| `fade_out_time` | `"1.5"` | Time it takes for the light to fade out.        |
| `r`       | `"150"` | Red component of the light color.               |
| `g`       | `"190"` | Green component of the light color.             |
| `b`       | `"230"` | Blue component of the light color.              |
| `_tags`   | `"enabled_in_hand,item_identified"` | Active when held and identified. |

### AudioComponent

Manages the sound effects associated with the shield.

| Attribute     | Value                               | Description                                     |
| :------------ | :---------------------------------- | :---------------------------------------------- |
| `file`        | `"data/audio/Desktop/projectiles.bank"` | Path to the audio bank file.                    |
| `event_root`  | `"player_projectiles/shield"`       | Root event name for shield sounds.              |
| `set_latest_event_position` | `"1"` | Sets the sound's position to the latest event. |
| `_tags`       | `"enabled_in_hand,item_identified"` | Active when held and identified. |

### LifetimeComponent

Determines how long the shield entity will exist.

| Attribute | Value   | Description                                     |
| :-------- | :------ | :---------------------------------------------- |
| `lifetime` | `"1800"` | The total lifetime of the entity in seconds.    |