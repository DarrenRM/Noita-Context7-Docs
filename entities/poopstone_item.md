---
title: Poopstone Item
category: entities
---

# Poopstone Item

This document details the `poopstone.xml` entity, which represents the "Poopstone" item in Noita. This item is characterized by its physical properties, its ability to inflict status effects, and its unique material conversion capabilities.

## Key Attributes and Components

The Poopstone entity is defined by several key components that dictate its behavior and appearance.

### Core Entity Tags

*   `hittable`: The entity can be hit by projectiles or other game elements.
*   `teleportable_NOT`: The entity cannot be teleported.
*   `item_physics`: The entity interacts with the game's physics system.
*   `item_pickup`: The entity can be picked up by the player.
*   `poopstone`: A custom tag identifying this specific item.

### Physics Components

*   **`PhysicsBodyComponent`**:
    *   `is_bullet="1"`: Allows the entity to act as a projectile.
    *   `hax_fix_going_through_ground="1"`: A fix to prevent the entity from clipping through the ground.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/items_gfx/kakke.png"`: Defines the visual sprite for the item in the world.
    *   `material="poop_box2d_hard"`: Specifies the physics material, influencing its interaction with the environment.
*   **`PhysicsThrowableComponent`**:
    *   `max_throw_speed="180"`: Sets the maximum speed when thrown.
    *   `throw_force_coeff="1.5"`: A coefficient affecting the force applied when throwing.
*   **`VelocityComponent`**: Manages the entity's velocity.

### Game Effect Components

These components define the status effects the Poopstone inflicts when held.

*   **`GameEffectComponent`**:
    *   `effect="FOOD_POISONING"`: Inflicts food poisoning.
    *   `effect="POISON"`: Inflicts poison.
    *   `effect="SLIMY"`: Makes the player slimy.
    *   `frames="-1"`: Indicates the effect is permanent as long as the item is held.

### Item Components

*   **`SpriteComponent`**:
    *   `image_file="data/items_gfx/in_hand/kakke_in_hand.png"`: Defines the sprite when the item is held in the player's hand.
*   **`ItemComponent`**:
    *   `item_name="$item_kakka"`: The internal name for the item (likely localized).
    *   `ui_description="$itemdesc_kakka"`: The description shown in the UI (likely localized).
    *   `ui_sprite="data/ui_gfx/items/kakke.png"`: The sprite used in the UI inventory.
    *   `is_pickable="1"`: Allows the item to be picked up.
    *   `is_equipable_forced="1"`: The item is automatically equipped when picked up.
    *   `preferred_inventory="QUICK"`: The item is placed in the quick inventory.
*   **`UIInfoComponent`**:
    *   `name="$item_kakka"`: The name displayed in UI elements.
*   **`AbilityComponent`**:
    *   `throw_as_item="1"`: Allows the item to be thrown as a projectile.

### Material Conversion Components

These are the core mechanics of the Poopstone, allowing it to transform various materials into "poo".

*   **`MagicConvertMaterialComponent`**:
    *   `to_material="poo"`: The target material for conversion.
    *   `radius="64"`: The area of effect for the conversion.
    *   `loop="1"`: The conversion effect will loop.
    *   `clean_stains="0"`: Does not clean existing stains.
    *   `is_circle="1"`: The conversion area is circular.
    *   **Specific conversions:**
        *   `from_material_tag="[liquid]"`: Converts liquids.
        *   `from_material_tag="[sand]"`: Converts sand.
        *   `from_material_tag="[molten]"`: Converts molten materials.
        *   A general component without `from_material_tag` is present, likely for other unspecified conversions or to extinguish fire (`extinguish_fire="1"`).

### Particle Emitters

*   **`SpriteParticleEmitterComponent`**:
    *   Responsible for emitting particles, likely visual effects associated with the item's presence or use.
    *   `sprite_file="data/particles/ray.xml"`: Uses a ray sprite for particles.
    *   `color.r="1" color.g="0.5" color.b="1" color.a="1.0"`: Sets an initial pinkish color.
    *   `scale_velocity.x="-0.3" scale.y="0"`: Particles shrink in width and grow in height.
    *   `randomize_velocity`: Particles are emitted with randomized velocities.
*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="poo"`: Emits particles of the "poo" material.
    *   `gravity.y="35"`: Particles are affected by gravity.
    *   `lifetime_min="1.0" lifetime_max="5.0"`: Particles have a lifespan between 1 and 5 seconds.
    *   `collide_with_grid="1"`: Particles can collide with the game grid.
    *   `render_on_grid="1"`: Particles are rendered on the grid.
    *   Two instances exist: one for cosmetic particles (`emit_cosmetic_particles="0"`) and one for actual material particles (`emit_cosmetic_particles="1"`).

### Lua Component

*   **`LuaComponent`**:
    *   `script_source_file="data/scripts/items/poopstone.lua"`: Links to an external Lua script for more complex logic.
    *   `execute_every_n_frame="20"`: The script executes every 20 frames.

## Summary

The Poopstone is a unique item in Noita that, when held, inflicts negative status effects (food poisoning, poison, slimy) and has the powerful ability to convert various liquids, sands, and molten materials into "poo" within a radius. It also has visual particle effects and is controlled by an external Lua script for advanced functionality. Its physics properties allow it to be thrown as a projectile.