---
title: Thunderstone Item
category: entities
---

# Thunderstone Item

This document details the Thunderstone item entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Attributes

The Thunderstone is an item that can be picked up and thrown, possessing electrical properties and granting electrical protection.

*   **Tags:** `hittable`, `teleportable_NOT`, `item_physics`, `item_pickup`, `thunderstone`
*   **Base File:** `data/entities/base_item_projectile.xml` - Inherits projectile and item base functionalities.

## Key Components

### ProjectileComponent

Defines the damage dealt by the item when used as a projectile.

*   **`damage_by_type.electricity`**: `0.5` - Deals 0.5 electrical damage.

### PhysicsBodyComponent

Governs the physical behavior of the item in the world.

*   **`is_bullet`**: `1` - Indicates it can act as a projectile.
*   **`hax_fix_going_through_ground`**: `1` - A fix to prevent it from falling through the ground.

### PhysicsImageShapeComponent

Defines the visual representation and collision shape of the item.

*   **`image_file`**: `data/items_gfx/smallgem_03.png` - Uses a small gem graphic for its physical form.
*   **`material`**: `gem_box2d` - Specifies the physics material.

### PhysicsThrowableComponent

Controls how the item can be thrown.

*   **`max_throw_speed`**: `180`
*   **`throw_force_coeff`**: `1.5`

### ElectricitySourceComponent

Enables the item to emit electricity.

*   **`radius`**: `24` - The radius of the electrical emission.
*   **`emission_interval_frames`**: `64` - How often electricity is emitted.

### GameEffectComponent

Applies passive effects when the item is held.

*   **`effect`**: `PROTECTION_ELECTRICITY` - Grants immunity to electricity.
*   **`effect`**: `FRIEND_THUNDERMAGE` - Makes the player appear as a friendly Thunder Mage.
*   **`frames`**: `-1` - Indicates the effect is permanent while held.

### SpriteComponent

Defines the visual sprite when the item is held in hand.

*   **`image_file`**: `data/items_gfx/thunderstone.png` - The specific sprite for the Thunderstone.

### ItemComponent

Defines the item's properties for inventory and interaction.

*   **`item_name`**: `$item_thunderstone` - Localized name.
*   **`ui_description`**: `$item_description_thunderstone` - Localized description.
*   **`ui_sprite`**: `data/ui_gfx/items/ingredient_1.png` - Sprite used in the UI.
*   **`is_pickable`**: `1` - Can be picked up.
*   **`is_equipable_forced`**: `1` - Can be equipped directly.
*   **`preferred_inventory`**: `QUICK` - Defaults to the quick inventory.

### AbilityComponent

Grants the item an ability, in this case, the ability to be thrown as an item.

*   **`throw_as_item`**: `1`

### SpriteParticleEmitterComponent (x2)

These components define particle effects associated with the Thunderstone.

*   **First Emitter:**
    *   **`sprite_file`**: `data/particles/ray.xml` - Uses a ray particle effect.
    *   **`lifetime`**: `1.5`
    *   **`color`**: `r="1" g="0.5" b="1" a="1.0"` - Pinkish-purple hue.
    *   **`scale_velocity`**: `x="-0.3" y="3"` - Particles shrink in X and grow in Y.
    *   **`emission_interval_min_frames`**: `3`
    *   **`emission_interval_max_frames`**: `6`
    *   **`emissive`**: `1`
    *   **`additive`**: `1`
    *   **`velocity_always_away_from_center`**: `1` - Particles move outwards.

*   **Second Emitter:**
    *   **`sprite_file`**: `data/particles/spark_electric.xml` - Uses an electric spark particle effect.
    *   **`gravity`**: `y="10"`
    *   **`emission_interval_min_frames`**: `1`
    *   **`emission_interval_max_frames`**: `3`
    *   **`randomize_rotation`**: `min="-3.1415" max="3.1415"`
    *   **`tags`**: `enabled_in_world`, `enabled_in_hand` - Active in world and when held.

### Base file: `data/entities/particles/water_electrocution.xml`

This indicates the Thunderstone entity also inherits properties from the `water_electrocution` particle effect, likely for visual or functional synergy.