---
title: Radioactive Barrel
category: entities
---

# Radioactive Barrel

This document details the configuration of the Radioactive Barrel entity in Noita, focusing on its physical properties, material interactions, and explosive behavior.

## Base Entity Configuration

The Radioactive Barrel inherits its core functionality from `base_item_physics2.xml`, indicating it's a physics-enabled item.

### `Base` Component

*   **`file`**: `data/entities/base_item_physics2.xml` - Inherits physics and item properties.

### `PhysicsBody2Component`

*   **`kill_entity_after_initialized`**: `0` - The entity does not immediately self-destruct upon initialization.

### `PhysicsImageShapeComponent`

*   **`image_file`**: `data/props_gfx/barrel_radioactive.png` - Specifies the visual sprite for the barrel.
*   **`material`**: `metal_rust_barrel` - Defines the physical material properties for collision and interaction.

## Material Inventory and Spill Behavior

This component governs what materials the barrel contains and how they are released.

### `MaterialInventoryComponent`

*   **`_enabled`**: `1` - The component is active.
*   **`drop_as_item`**: `0` - The barrel does not drop as a usable item upon death.
*   **`on_death_spill`**: `1` - The barrel's contents will spill out when it dies.
*   **`leak_on_damage_percent`**: `0.999` - The barrel will leak its contents when it reaches 99.9% damage.
*   **`audio_collision_size_modifier_amount`**: `0.8` - Modifies the sound of collisions based on the barrel's size.

#### `count_per_material_type`

*   **`Material material="radioactive_liquid" count="750"`**: The barrel contains 750 units of `radioactive_liquid`.

## Damage and Destruction Properties

This component defines how the barrel takes damage and what happens upon destruction.

### `DamageModelComponent`

*   **`air_needed`**: `0` - The entity does not require air to function.
*   **`blood_material`**: `radioactive_liquid` - The material associated with damage effects, likely for visual or particle generation.
*   **`drop_items_on_death`**: `0` - No specific items are dropped upon death, beyond its contents.
*   **`falling_damage_damage_max`**: `1.2`
*   **`falling_damage_damage_min`**: `0.1`
*   **`falling_damage_height_max`**: `250`
*   **`falling_damage_height_min`**: `70`
*   **`falling_damages`**: `0` - Falling damage is not directly applied to the entity itself.
*   **`fire_damage_amount`**: `0.4` - The amount of damage taken from fire.
*   **`fire_probability_of_ignition`**: `0` - The barrel cannot ignite from fire.
*   **`critical_damage_resistance`**: `1` - No resistance to critical damage.
*   **`hp`**: `0.2` - The barrel has very low health.
*   **`is_on_fire`**: `0` - The barrel is not initially on fire.
*   **`materials_create_messages`**: `0` - No messages are created when materials interact with it.
*   **`materials_damage`**: `1` - The barrel takes damage from certain materials.
*   **`materials_that_damage`**: `fire,lava,acid` - Materials that can damage the barrel.
*   **`materials_how_much_damage`**: `0.0002,0.0001,0.001` - The damage values for `fire`, `lava`, and `acid` respectively.
*   **`ragdoll_filenames_file`**: `""` - No ragdoll files are used.
*   **`ragdoll_material`**: `""` - No specific ragdoll material.

#### `damage_multipliers`

*   **`melee`**: `0.1` - Melee attacks deal 10% of their normal damage to the barrel.

## Explosion on Damage Component

This component defines the explosive properties of the barrel.

### `ExplodeOnDamageComponent`

*   **`explode_on_death_percent`**: `1` - The barrel will explode when it reaches 100% damage (death).
*   **`explode_on_damage_percent`**: `0.0` - The barrel will not explode from partial damage.
*   **`physics_body_modified_death_probability`**: `0.9` - There's a 90% chance of explosion if the physics body is modified upon death.
*   **`physics_body_destruction_required`**: `0.15` - The physics body needs to be at least 15% destroyed for a potential explosion.

#### `config_explosion`

*   **`never_cache`**: `0` - The explosion can be cached.
*   **`damage`**: `2.6` - The base damage dealt by the explosion.
*   **`camera_shake`**: `40` - The intensity of camera shake during the explosion.
*   **`explosion_radius`**: `40` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_032.xml` - The particle effect used for the explosion visual.
*   **`explosion_sprite_lifetime`**: `10` - The duration of the explosion sprite.
*   **`create_cell_probability`**: `50` - 50% chance to create cells (liquid/gas) from the explosion.
*   **`hole_destroy_liquid`**: `0` - The explosion does not destroy liquids.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_green.xml` - Loads a specific entity for the explosion effect.
*   **`hole_enabled`**: `1` - The explosion can create holes.
*   **`ray_energy`**: `2500000` - The energy of the explosion's rays.
*   **`particle_effect`**: `1` - Particle effects are enabled for the explosion.
*   **`damage_mortals`**: `1` - The explosion damages mortal entities.
*   **`physics_explosion_power.min`**: `1.7` - Minimum physics force applied by the explosion.
*   **`physics_explosion_power.max`**: `2.3` - Maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Physics objects can be thrown by the explosion.
*   **`shake_vegetation`**: `1` - The explosion shakes vegetation.
*   **`sparks_count_max`**: `20` - Maximum number of sparks generated.
*   **`sparks_count_min`**: `7` - Minimum number of sparks generated.
*   **`sparks_enabled`**: `1` - Sparks are enabled.
*   **`stains_enabled`**: `1` - Stains are enabled.
*   **`stains_radius`**: `15` - The radius of stains created by the explosion.
*   **`delay.min`**: `1` - Minimum delay before the explosion.
*   **`delay.max`**: `4` - Maximum delay before the explosion.
*   **`explosion_delay_id`**: `1` - Identifier for the explosion delay.
*   **`audio_event_name`**: `explosions/barrel_sludge` - The sound event played for the explosion.

## Audio Components

These components handle the sound effects associated with the barrel.

### `AudioLoopComponent`

*   **`_tags`**: `sound_spray` - Tags the component for specific sound behaviors.
*   **`file`**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound.
*   **`event_name`**: `materials/spray` - The specific sound event name.
*   **`volume_autofade_speed`**: `0.25` - Controls the speed of volume fading.

### `AudioComponent`

*   **`file`**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound.
*   **`event_root`**: `collision/metalhollow` - The root event name for collision sounds.
*   **`set_latest_event_position`**: `1` - Sets the sound's position to the latest event.