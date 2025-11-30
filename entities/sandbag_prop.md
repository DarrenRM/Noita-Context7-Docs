---
title: Sandbag Prop
category: entities
---

# Sandbag Prop

This document describes the `physics_sandbag.xml` entity, a prop used in Noita. It's a physics-enabled object that can be damaged and break apart, spilling its contents.

## Key Components and Attributes

### Base Entity

The sandbag inherits its core physics behavior from `base_item_physics.xml`.

### Physics Image Shape Component

This component defines the visual representation and physical properties of the sandbag.

*   **`image_file`**: `data/props_gfx/sandbag.png` - Specifies the texture used for the sandbag.
*   **`material`**: `rock_box2d` - Defines the base physical material for collision and interaction.
*   **`centered`**: `1` - Indicates the image is centered on the entity's origin.

### Material Inventory Component

This component manages the materials contained within the sandbag and how they are handled upon damage or death.

*   **`drop_as_item`**: `0` - The sandbag itself does not drop as a collectible item when destroyed.
*   **`on_death_spill`**: `1` - When the sandbag is destroyed, its contents will spill out.
*   **`leak_on_damage_percent`**: `0.5` - If the sandbag takes damage exceeding 50% of its HP, it will start to leak its contents.
*   **`audio_collision_size_modifier_amount`**: `0.8` - Affects the volume of collision sounds.

#### Material Counts

*   **`Material material="sand" count="200"`**: The sandbag contains 200 units of `sand` material.

### Damage Model Component

This component governs how the sandbag reacts to damage.

*   **`hp`**: `3.0` - The sandbag has 3 hit points.
*   **`falling_damage_damage_max`**: `1.2` - Maximum damage dealt by falling.
*   **`falling_damage_damage_min`**: `0.1` - Minimum damage dealt by falling.
*   **`falling_damage_height_max`**: `250` - Maximum height from which falling damage is calculated.
*   **`falling_damage_height_min`**: `70` - Minimum height from which falling damage is calculated.
*   **`fire_damage_amount`**: `0.4` - Damage taken from fire.
*   **`critical_damage_resistance`**: `1` - Indicates resistance to critical damage.

#### Damage Multipliers

*   **`melee="0.1"`**: Melee attacks deal only 10% of their normal damage to the sandbag.

### Destruction Behavior

The sandbag is tagged as `mortal`, which is a prerequisite for it to be able to explode.

*   **`physics_body_destruction_required`**: (Commented out, but implies a threshold for destruction)
*   **`physics_body_modified_death_probability`**: (Commented out, but implies a probability of explosion upon destruction)