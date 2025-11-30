---
title: Newsun Item
category: entities
---

---

# Newsun Item

This document details the `newsun.xml` entity, representing a powerful item in Noita that functions similarly to a miniature sun. It possesses various damaging and material-altering capabilities.

## Core Components

The `newsun.xml` entity is built upon several key components that define its behavior and appearance.

### Base Entity

*   **`Base file="data/entities/base_item_projectile.xml"`**: Inherits fundamental properties from the base projectile item, suggesting it can be thrown or wielded.

### Physics and Movement

*   **`PhysicsBodyComponent`**: Defines the physical presence of the sun, with properties like `allow_sleep="0"` and `fixed_rotation="0"` indicating it's always active and can rotate.
*   **`PhysicsKeepInWorldComponent`**: Ensures the sun remains within the game world boundaries.
*   **`VelocityComponent`**: Allows the sun to have velocity, affecting physics bodies.

### Visuals

*   **`SpriteComponent` (Fog of War)**:
    *   `image_file="data/particles/fog_of_war_hole_huge.png"`
    *   `fog_of_war_hole="1"`: Creates a visual "hole" in the fog of war around the sun.
*   **`SpriteComponent` (Sun GFX)**:
    *   `image_file="data/props_gfx/sun_big.png"`
    *   `emissive="1"`: Makes the sprite emit light.
    *   `additive="1"`: Blends the sprite with the background additively, creating a bright glow.

### Item Information

*   **`UIInfoComponent`**:
    *   `name="$item_seed_e"`: Assigns a localized name to the item, likely "Sun Seed" or similar.

## Core Functionality

The sun's destructive and transformative power is primarily handled by the following components:

### Material Conversion

The `MagicConvertMaterialComponent` is used multiple times to alter the environment around the sun.

*   **Component 1 (General Conversion)**:
    *   `to_material="lava"`: Converts nearby materials to lava.
    *   `convert_entities="1"`: Also converts entities within its radius.
    *   `radius="100"`: The radius of this conversion effect.
    *   `loop="1"`: The conversion effect repeats.
*   **Component 2 (Alchemy Conversion)**:
    *   `from_material_tag="[alchemy]"`: Specifically targets materials tagged as "alchemy".
    *   `to_material="lava"`: Converts these to lava.
    *   `radius="230"`: A larger radius for this specific conversion.
*   **Component 3 (Ignition)**:
    *   `ignite_materials="1"`: Causes nearby materials to ignite.
    *   `fan_the_flames="1"`: Enhances the spread of fire.
    *   `radius="270"`: The largest radius for ignition.

### Environmental Effects

*   **`CellEaterComponent`**:
    *   `radius="190"`: Defines the radius within which cells (materials) are "eaten".
    *   `eat_probability="80"`: High probability of consuming materials.
    *   `ignored_material="gem_box2d_yellow_sun"`: Prevents the sun from consuming itself or similar sun-like gems.

### Area Damage

Multiple `AreaDamageComponent` instances create concentric damage zones.

*   **Inner Zone (Curse Damage)**:
    *   `aabb_min/max`: Defines a small square area (approx. 244x244 units).
    *   `damage_per_frame="2.14"`: Significant damage.
    *   `damage_type="DAMAGE_CURSE"`: Applies curse damage.
*   **Middle Zone (Explosion Damage)**:
    *   `aabb_min/max`: Defines a larger square area (approx. 380x380 units).
    *   `damage_per_frame="1.05"`: Moderate damage.
    *   `damage_type="DAMAGE_EXPLOSION"`: Applies explosion damage.
*   **Outer Zone (Fire Damage)**:
    *   `aabb_min/max`: Defines the largest square area (approx. 560x560 units).
    *   `damage_per_frame="0.61"`: Lower damage.
    *   `damage_type="DAMAGE_FIRE"`: Applies fire damage.

### Particle Effects

Two `ParticleEmitterComponent` instances generate visual effects.

*   **Yellow Sparks**:
    *   `emitted_material_name="spark_yellow"`: Emits yellow sparks.
    *   `count_min/max="40/60"`: Emits a moderate number of particles.
    *   `lifetime_min/max="0.1/2.4"`: Particles have a short to medium lifespan.
    *   `render_ultrabright="1"`: Particles are rendered very brightly.
*   **Regular Sparks**:
    *   `emitted_material_name="spark"`: Emits standard sparks.
    *   Similar parameters to the yellow sparks, contributing to the visual intensity.

### Other Components

*   **`BlackHoleComponent`**:
    *   `particle_attractor_force="6"`: Pulls in nearby particles.
    *   `radius="280"`: The radius of the black hole effect.
*   **`AudioLoopComponent`**:
    *   `event_name="misc/sun/size_3_loop"`: Plays a looping sound effect associated with a large sun.
*   **`MusicEnergyAffectorComponent`**:
    *   `energy_target="1.0"`: Likely influences music or game energy levels.
*   **`LooseGroundComponent`**:
    *   Attached to an inner `Entity`, this component causes nearby ground to break apart over time, adding to the destructive effect.
*   **`LuaComponent`**:
    *   `script_source_file="data/scripts/buildings/sun/sun_controls.lua"`: Executes Lua scripts for controlling the sun's behavior.
    *   `script_source_file="data/scripts/buildings/sun/sun_collision.lua"`: Executes Lua scripts related to the sun's collision interactions.