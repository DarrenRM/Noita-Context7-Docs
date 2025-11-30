---
title: Beer Bottle Item
category: entities
---

# Beer Bottle Item

This document describes the `beer_bottle.xml` entity, which represents a throwable beer bottle item in Noita. It functions as a potion with unique properties related to material suction and leakage.

## Core Components

### Physics and Collision

*   **`PhysicsBodyComponent`**: Defines the physical presence of the bottle, allowing it to interact with the game world.
    *   `allow_sleep`: `1` - The physics body can enter a sleep state when not in motion.
    *   `is_bullet`: `1` - Allows the object to be treated as a projectile.
    *   `on_death_leave_physics_body`: `1` - The physics body persists even after the entity is destroyed.
*   **`PhysicsImageShapeComponent`**: Defines the visual shape and material of the bottle's physical body.
    *   `image_file`: `data/items_gfx/beer_bottle.png` - The sprite used for the physical representation.
    *   `material`: `glass_box2d` - The material type for physics interactions.
*   **`PhysicsThrowableComponent`**: Enables the bottle to be thrown.
    *   `max_throw_speed`: `180`
    *   `throw_force_coeff`: `1.5`
*   **`ProjectileComponent`**: Configures the bottle as a projectile.
    *   `lifetime`: `-1` - The projectile does not expire on its own.
    *   `penetrate_entities`: `1` - The projectile can pass through other entities.
*   **`PhysicsBodyCollisionDamageComponent`**: Deals damage upon collision based on speed.
    *   `speed_threshold`: `80.0`

### Potion and Material Handling

*   **`LuaComponent` (script_source_file)**: Executes `data/scripts/items/potion.lua` when the item is added, likely for initial potion setup.
    *   `execute_on_added`: `1`
    *   `remove_after_executed`: `1`
*   **`LuaComponent` (script_item_picked_up)**: Executes `data/scripts/items/potion_effect.lua` when the item is picked up, applying its effects.
    *   `remove_after_executed`: `1`
*   **`PotionComponent`**: Defines the bottle's behavior as a potion.
    *   `spray_velocity_coeff`: `75`
    *   `spray_velocity_normalized_min`: `0.75`
    *   `body_colored`: `0` - The potion itself is not colored.
    *   `never_color`: `1` - Prevents the potion from being colored by external factors.
*   **`MaterialSuckerComponent`**: Allows the bottle to suck up nearby materials.
    *   `barrel_size`: `1000`
    *   `num_cells_sucked_per_frame`: `5`
*   **`MaterialInventoryComponent`**: Manages the materials contained within the bottle.
    *   `on_death_spill`: `1` - Materials spill out upon death.
    *   `leak_pressure_min`: `0.07` (Note: Duplicate attribute, likely intended to be different values or one is a typo)
    *   `leak_on_damage_percent`: `1` - Leaks when damaged.
    *   `min_damage_to_leak`: `0.0` - Leaks even with minimal damage.
    *   `death_throw_particle_velocity_coeff`: `0.5`

### Damage and Destruction

*   **`DamageModelComponent`**: Defines the bottle's health and how it reacts to damage.
    *   `hp`: `0.5` - Low health, easily breakable.
    *   `materials_damage`: `1` - Can be damaged by certain materials.
    *   `materials_that_damage`: `lava` - Specifically damaged by lava.
    *   `materials_how_much_damage`: `0.001` - Deals minimal damage to itself from materials.
*   **`ExplodeOnDamageComponent`**: Configures explosion behavior upon taking damage.
    *   `explode_on_death_percent`: `1` - Explodes when health reaches zero.
    *   `explode_on_damage_percent`: `0` - Does not explode from partial damage.
    *   `physics_body_destruction_required`: `0.51`
    *   `config_explosion`: Defines the parameters of the explosion.
        *   `damage`: `0` - The explosion itself does not deal direct damage.
        *   `camera_shake`: `10`
        *   `explosion_radius`: `3`
        *   `ray_energy`: `100000`
        *   `physics_explosion_power.max`: `5`

## Item and UI Components

*   **`SpriteComponent`**: Defines the visual sprite when the item is held in hand.
    *   `image_file`: `data/items_gfx/beer_bottle.png`
*   **`ItemComponent`**: Standard item properties.
    *   `item_name`: `$item_potion` - Refers to a localized name.
    *   `is_pickable`: `1`
    *   `is_equipable_forced`: `1` - Can be equipped directly.
    *   `ui_sprite`: `data/items_gfx/beer_bottle.png` - Sprite for UI elements.
    *   `ui_description`: `$item_description_potion` - Refers to a localized description.
    *   `preferred_inventory`: `QUICK`
*   **`AbilityComponent`**: Grants abilities to the item.
    *   `ui_name`: `$item_kaljapullo` - Localized name for the ability.
    *   `throw_as_item`: `1` - Can be thrown as a distinct item.
*   **`UIInfoComponent`**: Provides information for the UI.
    *   `name`: `$item_kaljapullo` - Localized name.

## Audio Components

*   **`AudioLoopComponent`**: Handles looping audio effects, specifically for spraying.
    *   `file`: `data/audio/Desktop/materials.bank`
    *   `event_name`: `materials/spray_potion`
*   **`AudioComponent`**: Handles one-off audio effects, such as collision sounds.
    *   `file`: `data/audio/Desktop/materials.bank`
    *   `event_root`: `collision/glass_potion`