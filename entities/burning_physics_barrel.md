---
title: Burning Physics Barrel
category: entities
---

# Burning Physics Barrel

This document details the configuration of the "Burning Physics Barrel" entity in Noita, useful for AI-assisted modding.

## Core Components

The burning barrel is a physics-enabled prop that contains flammable oil and explodes when damaged or sufficiently heated.

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits fundamental physics and item properties.
    *   **`PhysicsBody2Component`**: Manages the physical body of the barrel.
        *   `kill_entity_after_initialized="0"`: The entity does not self-destruct immediately after being spawned.
    *   **`PhysicsImageShapeComponent`**: Defines the visual representation and collision shape.
        *   `image_file="data/props_gfx/barrel_burning.png"`: Specifies the sprite for the barrel.
        *   `material="metal_rust_barrel"`: The material type for physics interactions.

### Material Inventory

*   **`MaterialInventoryComponent`**: Manages the materials contained within the barrel.
    *   `drop_as_item="0"`: The barrel does not drop as a usable item upon destruction.
    *   `on_death_spill="1"`: Spills its contents when destroyed.
    *   `leak_on_damage_percent="0.5"`: Begins leaking when 50% of its HP is lost.
    *   **`count_per_material_type`**: Defines the contained materials.
        *   `Material material="oil" count="300"`: Contains 300 units of oil.

### Damage and Destruction

*   **`DamageModelComponent`**: Governs how the barrel takes damage and reacts to environmental hazards.
    *   `air_needed="0"`: Does not require air to function or be damaged.
    *   `blood_material="oil"`: Oil is treated as its "blood" for certain damage calculations.
    *   `falling_damage_damage_max="1.2"`: Maximum damage from falling.
    *   `falling_damage_damage_min="0.1"`: Minimum damage from falling.
    *   `falling_damage_height_max="250"`: Maximum height for falling damage to apply.
    *   `falling_damage_height_min="70"`: Minimum height for falling damage to apply.
    *   `fire_damage_amount="0.4"`: Amount of damage taken from fire per tick.
    *   `hp="0.2"`: Very low hit points, making it easily destructible.
    *   `materials_damage="1"`: Takes damage from contact with specific materials.
    *   `materials_that_damage="fire,lava,acid"`: Materials that inflict damage.
    *   `materials_how_much_damage="0.0002,0.0001,0.001"`: Damage values for fire, lava, and acid respectively.
    *   **`damage_multipliers`**: Modifies incoming damage.
        *   `melee="0.1"`: Takes only 10% of melee damage.

*   **`ExplodeOnDamageComponent`**: Handles the explosion mechanics.
    *   `explode_on_death_percent="1"`: Guarantees an explosion upon death.
    *   `explode_on_damage_percent="0.0"`: Can explode even with minimal damage.
    *   `physics_body_destruction_required="0.15"`: Requires 15% of its physics body to be destroyed before triggering an explosion.
    *   `physics_body_modified_death_probability="0.9"`: 90% chance of exploding if the destruction threshold is met.
    *   **`config_explosion`**: Defines the explosion's properties.
        *   `damage="2.6"`: Base damage of the explosion.
        *   `camera_shake="40"`: Intensity of camera shake.
        *   `explosion_radius="24"`: Radius of the explosion.
        *   `explosion_sprite="data/particles/explosion_032.xml"`: Visual effect for the explosion.
        *   `load_this_entity="data/entities/particles/particle_explosion/main.xml"`: Entity to load for the explosion effect.
        *   `hole_enabled="1"`: Creates holes in terrain.
        *   `ray_energy="4000000"`: Energy of the explosion's damaging rays.
        *   `physics_explosion_power.min="1.9"`: Minimum force of the physics-based explosion.
        *   `physics_explosion_power.max="2.5"`: Maximum force of the physics-based explosion.
        *   `sparks_enabled="1"`: Creates sparks.
        *   `stains_enabled="1"`: Creates stains on surfaces.
        *   `delay.min="1"`: Minimum delay before explosion.
        *   `delay.max="4"`: Maximum delay before explosion.

## Visual and Audio Effects

### Light and Fire

*   **`Entity`**: Contains sub-entities for visual and auditory effects.
    *   **`LightComponent`**: Emits light.
        *   `radius="96"`: The radius of the light.
        *   `fade_out_time="1.5"`: How long the light fades out.
    *   **`TorchComponent`**: Simulates a burning torch effect.
        *   `fire_audio_weight="1"`: Contributes to fire sound intensity.
        *   `suffocation_check_offset_y="-3"`: Offset for checking if the fire is suffocated.
    *   **`SpriteAnimatorComponent`**: Handles sprite animations.

### Particle Emitters

*   **`Base file="data/entities/base_torch_particle.xml"`**: Inherits particle emitter configurations for fire effects.
    *   **`ParticleEmitterComponent`**: Multiple instances create fire particles around the barrel.
        *   `x_pos_offset_min="-3"`, `x_pos_offset_max="2"`: Offsets for particle emission position.

### Audio

*   **`AudioLoopComponent`**: Plays a looping sound effect.
    *   `event_name="materials/spray"`: The specific sound event.
*   **`AudioComponent`**: Plays a sound on collision.
    *   `event_root="collision/metalhollow"`: The root event for collision sounds.