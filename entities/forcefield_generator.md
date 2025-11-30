---
title: Forcefield Generator
category: entities
---

# Forcefield Generator

This entity spawns a protective forcefield when active. It has a visual representation, emits light, and can explode when destroyed.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits physics properties for an item.
    *   **`PhysicsBodyComponent`**: `is_static="1"` means the generator itself does not move.
    *   **`PhysicsImageShapeComponent`**: Defines the visual shape and material (`steel`) of the generator.
        *   `image_file="data/props_gfx/forcefield_generator.png"`: The sprite for the generator.

### Visuals and Effects

*   **`SpriteComponent`**:
    *   `image_file="data/props_gfx/forcefield_generator_light.xml"`: The sprite that emits light.
    *   `emissive="1"`: Makes the sprite glow.
    *   `z_index="0.2"`: Controls rendering order.

### Damage and Destruction

*   **`DamageModelComponent`**:
    *   `hp="30"`: The health of the generator.
    *   `materials_that_damage="fire,lava,acid"`: Materials that can damage the generator.
    *   `materials_how_much_damage="0.0002,0.0001,0.001"`: The damage values for the respective materials.
    *   `critical_damage_resistance="1"`: No resistance to critical damage.
    *   `damage_multipliers`:
        *   `melee="0.1"`: Takes 10% damage from melee attacks.
        *   `electricity="0"`: Immune to electricity damage.

*   **`ExplodeOnDamageComponent`**:
    *   `explode_on_death_percent="1"`: Always explodes upon death.
    *   `physics_body_modified_death_probability="0.9"`: High chance of physics body destruction on death.
    *   `config_explosion`: Defines the explosion properties.
        *   `damage="2.6"`: Damage dealt by the explosion.
        *   `camera_shake="10"`: Intensity of camera shake.
        *   `explosion_radius="16"`: The radius of the explosion.
        *   `load_this_entity="data/entities/projectiles/thunderball.xml"`: Spawns a `thunderball` projectile upon explosion.
        *   `audio_event_name="explosions/electric"`: The sound effect for the explosion.

### Behavior

*   **`LuaComponent`**:
    *   `script_source_file="data/scripts/props/forcefield_generator.lua"`: Links to the Lua script that controls the generator's behavior.
    *   `execute_every_n_frame="8"`: The script runs every 8 frames.

## Shield Entity

This nested entity defines the actual forcefield.

### Shield Properties

*   **`InheritTransformComponent`**: Positions and rotates the shield relative to the generator.
    *   `Transform position.x="8" position.y="-8" rotation="-1.5707"`: Offsets and rotates the shield.

*   **`EnergyShieldComponent`**:
    *   `recharge_speed="0.25"`: How quickly the shield recharges.
    *   `radius="20.0"`: The radius of the shield.
    *   `energy="2.0"`: Current energy of the shield.
    *   `max_energy="3.0"`: Maximum energy capacity.
    *   `sector_degrees="320"`: The shield covers 320 degrees, leaving a gap.

### Shield Visuals (Particles)

Multiple `ParticleEmitterComponent`s are used to create the visual effect of the shield.

*   **`_tags="enabled_while_shielding"`**: These emitters are active only when the shield is up.
*   **`emitted_material_name="plasma_fading"`**: The type of particle used.
*   **`area_circle_radius`**: Defines the area where particles are emitted.
*   **`area_circle_sector_degrees`**: Controls the angular coverage of the particles.
*   **`emission_interval_min_frames`/`max_frames`**: Controls the rate of particle emission.
*   **`emit_cosmetic_particles="1"`**: Ensures particles are rendered.

Specific tags like `shield_ring` and `shield_hit` likely control different visual aspects of the shield's state.

### Shield Lighting

*   **`LightComponent`**:
    *   `radius="60"`: The radius of the light emitted by the shield.
    *   `r="150" g="190" b="230"`: The color of the light (a bluish-white).

### Shield Audio

*   **`AudioComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: The audio bank containing the sound.
    *   `event_root="player_projectiles/shield"`: The specific sound event for the shield.