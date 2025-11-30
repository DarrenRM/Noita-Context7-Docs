---
title: Vault Apparatus 01
category: data
---

# Vault Apparatus 01

This entity represents a "Vault Apparatus 01", a prop that can explode and release alcohol gas. It's designed to be a static object that reacts to damage and environmental hazards.

## Key Components and Attributes

### Base Entity (`Base`)

*   **`file="data/entities/base_item_physics.xml"`**: Inherits physics properties from a base item.
*   **`is_static="1"`**: The apparatus is fixed in place and does not move on its own.
*   **`on_death_leave_physics_body="0"`**: When destroyed, it does not leave a physics body behind.

### Visuals (`PhysicsImageShapeComponent`)

*   **`image_file="data/props_gfx/vault_apparatus_01.png"`**: Specifies the visual sprite for the apparatus.
*   **`material="steel"`**: The material used for collision and physics interactions.
*   **`centered="0"`**: The image is not centered on its origin point.

### Material Inventory (`MaterialInventoryComponent`)

This component manages the materials contained within the apparatus.

*   **`drop_as_item="0"`**: The apparatus does not drop as a collectible item upon death.
*   **`on_death_spill="1"`**: When destroyed, its contents are spilled.
*   **`leak_pressure_min="0.1"`, `leak_pressure_max="0.3"`**: Defines the pressure range for material leakage.
*   **`leak_on_damage_percent="0.5"`**: 50% of its contents will leak when it takes damage.
*   **`audio_collision_size_modifier_amount="0.8"`**: Modifies the sound of collisions.

#### Material Contents

| Material      | Count |
| :------------ | :---- |
| `alcohol_gas` | 500   |

### Damage Model (`DamageModelComponent`)

Defines how the apparatus takes damage and its resistances.

*   **`hp="50"`**: The apparatus has 50 hit points.
*   **`materials_damage="lava,acid"`**: Lava and acid will damage this entity.
*   **`materials_how_much_damage="0.0002,0.0001,0.001"`**: Specifies the damage values for the materials that damage it.
*   **`critical_damage_resistance="1"`**: Immune to critical damage.
*   **`falling_damages="0"`**: Does not take damage from falling.

#### Damage Multipliers

| Damage Type | Multiplier |
| :---------- | :--------- |
| `melee`     | `0.1`      |

### Explosion on Damage (`ExplodeOnDamageComponent`)

Controls the explosion behavior of the apparatus.

*   **`explode_on_death_percent="1"`**: Guarantees an explosion upon death.
*   **`explode_on_damage_percent="0.0"`**: Does not explode solely from taking damage (relies on destruction threshold).
*   **`physics_body_destruction_required="0.15"`**: An explosion is triggered when 15% of its physics body is destroyed.
*   **`physics_body_modified_death_probability="0.9"`**: If the destruction threshold is met, there's a 90% chance of an explosion.

#### Explosion Configuration (`config_explosion`)

*   **`damage="2.6"`**: The explosion deals 2.6 damage.
*   **`camera_shake="40"`**: Causes significant camera shake.
*   **`explosion_radius="45"`**: The explosion covers a radius of 45 units.
*   **`explosion_sprite="data/particles/explosion_032.xml"`**: Uses a specific particle effect for the explosion.
*   **`load_this_entity="data/entities/projectiles/deck/mist_alcohol.xml"`**: Spawns "mist\_alcohol" entities upon explosion.
*   **`ray_energy="4000000"`**: High energy for the explosion's ray effects.
*   **`physics_explosion_power.min="1.9"`, `physics_explosion_power.max="2.5"`**: Defines the force of the physics-based explosion.
*   **`delay.min="1"`, `delay.max="4"`**: The explosion has a random delay between 1 and 4 frames.

### Particle Emitters (`ParticleEmitterComponent`)

Two emitters are present: one for fire and one for alcohol gas.

*   **Fire Emitter**:
    *   `emitted_material_name="fire"`
    *   `count_min="5"`, `count_max="10"`
    *   `lifetime_min="0.1"`, `lifetime_max="0.75"`
    *   `is_emitting="1"`
*   **Alcohol Gas Emitter**:
    *   `emitted_material_name="alcohol_gas"`
    *   `count_min="10"`, `count_max="50"`
    *   `is_emitting="1"`

### Audio Components (`AudioLoopComponent`, `AudioComponent`)

*   **`AudioLoopComponent`**: Plays a looping sound effect tagged as "sound\_spray" from `materials.bank`.
*   **`AudioComponent`**: Plays a "collision/metalhollow" sound event from `materials.bank` upon collision.