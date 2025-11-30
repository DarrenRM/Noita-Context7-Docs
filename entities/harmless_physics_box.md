---
title: Harmless Physics Box
category: data/entities
---

# Harmless Physics Box

This entity represents a simple, harmless physics box. It's designed to interact with the physics engine but does not pose a threat to the player.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits core physics and item functionalities.

### Physics Body 2 Component

*   **`kill_entity_after_initialized="0"`**: The entity will not be destroyed immediately after its physics are initialized.

### Physics Image Shape Component

*   **`centered="1"`**: The image used for the physics shape is centered.
*   **`image_file="data/props_gfx/box.png"`**: Specifies the visual asset for the box.
*   **`material="wood_prop"`**: Defines the physical material properties, influencing interactions.

### Damage Model Component

This component defines how the entity reacts to damage.

*   **`air_needed="0"`**: Does not require air to function or survive.
*   **`drop_items_on_death="0"`**: No items are dropped when the entity is destroyed.
*   **`falling_damage_damage_max="1.2"`**: Maximum damage dealt from falling.
*   **`falling_damage_damage_min="0.1"`**: Minimum damage dealt from falling.
*   **`falling_damage_height_max="250"`**: Maximum height at which falling damage is calculated.
*   **`falling_damage_height_min="70"`**: Minimum height at which falling damage is calculated.
*   **`falling_damages="0"`**: The entity itself does not deal falling damage to others.
*   **`fire_damage_amount="0.4"`**: Amount of damage taken from fire.
*   **`fire_probability_of_ignition="0"`**: Cannot be ignited by fire.
*   **`critical_damage_resistance="1"`**: No resistance to critical damage.
*   **`hp="5.0"`**: The entity has 5 hit points.
*   **`is_on_fire="0"`**: Starts with no fire effect.
*   **`materials_create_messages="0"`**: Does not create messages when materials interact.
*   **`materials_damage="0"`**: Materials do not directly damage this entity.
*   **`ui_report_damage="0"`**: Damage taken is not reported in the UI.

#### Damage Multipliers

*   **`melee="0.1"`**: Takes only 10% of the damage from melee attacks.

### Destruction Parameters (Commented Out)

The following parameters are commented out but indicate potential for destruction behavior:

*   `physics_body_destruction_required` (0.0-1.0): Threshold for physics body destruction before potential explosion.
*   `physics_body_modified_death_probability` (0.0-1.0): Probability of exploding if destruction threshold is met.