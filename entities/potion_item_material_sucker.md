---
title: Potion Item (Material Sucker)
category: entities
---

# Potion Item (Material Sucker)

This entity defines a potion item in Noita that has the unique ability to suck up and store materials. It functions as a throwable item that can be picked up and used by the player.

## Key Components and Attributes

### Physics and Collision

*   **`PhysicsBodyComponent`**: Defines the physical properties of the item, such as damping, rotation, and collision behavior.
    *   `is_bullet="1"`: Allows the item to pass through other entities.
    *   `hax_fix_going_through_ground="1"`: A fix for potential ground-clipping issues.
*   **`PhysicsImageShapeComponent`**: Renders the visual representation of the item using a specified image and material.
    *   `image_file="data/items_gfx/potion_normals.png"`: The texture used for the item's physics shape.
    *   `material="potion_glass_box2d"`: The physics material defining its interaction properties.
*   **`PhysicsThrowableComponent`**: Enables the item to be thrown with specific force and speed.
    *   `max_throw_speed="180"`
    *   `throw_force_coeff="1.5"`
*   **`ProjectileComponent`**: Configures the item as a projectile.
    *   `penetrate_entities="1"`: Allows the projectile to pass through multiple entities.
*   **`VelocityComponent`**: Manages the item's velocity.
*   **`PhysicsBodyCollisionDamageComponent`**: Deals damage to other entities upon collision based on speed.
    *   `speed_threshold="80.0"`: The minimum speed required to deal collision damage.

### Material Sucking and Inventory

*   **`MaterialSuckerComponent`**: The core component responsible for sucking up materials.
    *   `material_type="1"`: Specifies the type of material it can suck (this value might need further context from game code).
    *   `barrel_size="1000"`: The capacity of the "barrel" for sucked materials.
    *   `num_cells_sucked_per_frame="10"`: How many material "cells" are absorbed per game frame.
    *   `randomized_position`: Defines a small random offset for where materials are sucked from relative to the item.
*   **`MaterialInventoryComponent`**: Manages the inventory of sucked materials.
    *   `drop_as_item="0"`: Prevents the sucked materials from being dropped as individual items upon death.
    *   `on_death_spill="1"`: Causes the stored materials to spill out upon the item's destruction.
    *   `leak_pressure_min`, `leak_on_damage_percent`: Controls how and when materials might leak out.
    *   `death_throw_particle_velocity_coeff`: Affects the velocity of particles when materials spill.

### Item and Ability

*   **`LuaComponent`**: Executes Lua scripts.
    *   `script_item_picked_up="data/scripts/items/potion_effect.lua"`: This script is executed when the item is picked up, likely handling initial setup or effects.
*   **`PotionComponent`**: A component specific to potion-like items, likely influencing their behavior when held or used.
    *   `spray_velocity_coeff`, `spray_velocity_normalized_min`: Parameters related to spraying effects.
*   **`SpriteComponent`**: Defines the visual sprite of the item when held in the player's hand.
    *   `image_file="data/items_gfx/potion.png"`: The texture for the item in hand.
*   **`ItemComponent`**: Standard item properties.
    *   `item_name="$item_potion"`: The internal name for the item.
    *   `is_pickable="1"`: Allows the item to be picked up.
    *   `is_equipable_forced="1"`: Forces the item to be equipped when picked up.
    *   `ui_sprite`, `ui_description`: References for the item's UI representation.
    *   `preferred_inventory="QUICK"`: Assigns the item to the quick inventory slot.
*   **`AbilityComponent`**: Grants abilities to the item.
    *   `ui_name="$item_potion_with_material"`: The name displayed in the UI when it has materials.
    *   `throw_as_item="1"`: Allows the item to be thrown as a distinct entity.
*   **`UIInfoComponent`**: Provides information for the UI.

### Visual and Audio Effects

*   **`SpriteParticleEmitterComponent`**: Creates particle effects.
    *   `sprite_file="data/particles/ray.xml"`: Uses a ray particle effect.
    *   Various parameters control the color, velocity, scale, and emission rate of the particles, suggesting a visual effect when the item is active or used.
*   **`AudioLoopComponent`**: Plays looping audio effects.
    *   `event_name="materials/spray_potion"`: Likely plays a sound when the potion is actively spraying or sucking.
*   **`AudioComponent`**: Plays one-off audio effects.
    *   `event_root="collision/glass_potion"`: Plays a sound upon collision, likely a breaking glass sound.

### Damage and Destruction

*   **`DamageModelComponent`**: Defines how the item takes damage and its resistance.
    *   `hp="0.5"`: The item has very low health.
    *   `materials_damage="1"`: The item can be damaged by certain materials.
    *   `materials_that_damage="lava"`: Specifically, lava damages this item.
*   **`ExplodeOnDamageComponent`**: Causes the item to explode under certain damage conditions.
    *   `explode_on_death_percent="1"`: Explodes when its health reaches 0.
    *   `config_explosion`: Defines the parameters of the explosion, including damage, radius, and particle effects.

---