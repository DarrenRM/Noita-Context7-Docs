---
title: Small Harmless Physics Box
category: entities
---

# Small Harmless Physics Box

This entity represents a small, harmless physics-enabled box. It's designed to be a simple prop that interacts with the physics engine and can be destroyed.

## Key Components and Attributes

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits core physics and item functionalities.

### Physics Image Shape Component

*   **`centered="1"`**: The image is centered within its physics shape.
*   **`image_file="data/props_gfx/box_small.png"`**: Specifies the visual sprite for the box.
*   **`material="wood_prop"`**: Defines the physical material properties, influencing interactions.

### Damage Model Component

This component governs how the entity reacts to damage.

*   **`hp="5.0"`**: The box has 5 hit points.
*   **`falling_damage_damage_max="1.2"`**: Maximum damage dealt from falling.
*   **`falling_damage_damage_min="0.1"`**: Minimum damage dealt from falling.
*   **`falling_damage_height_max="250"`**: Maximum height at which falling damage is calculated.
*   **`falling_damage_height_min="70"`**: Minimum height at which falling damage is calculated.
*   **`fire_damage_amount="0.4"`**: Amount of damage taken from fire.
*   **`critical_damage_resistance="1"`**: No resistance to critical damage.
*   **`ui_report_damage="0"`**: Damage taken by this entity will not be reported in the UI.

#### Damage Multipliers

*   **`melee="0.1"`**: Takes only 10% of normal damage from melee attacks.

### Destruction Behavior

*   **`physics_body_destruction_required`**: (Commented out) This attribute, if present, would define the threshold of destruction required for certain effects.
*   **`physics_body_modified_death_probability`**: (Commented out) This attribute, if present, would define the probability of an explosion occurring if the destruction threshold is met.