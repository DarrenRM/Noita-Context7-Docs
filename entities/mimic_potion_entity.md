---
title: Mimic Potion Entity
category: entities
---

# Mimic Potion Entity

This document details the `mimic_potion.xml` entity, which defines the behavior and appearance of the Mimic Potion creature in Noita. It inherits properties from base potion and enemy entities, with significant modifications to create its unique functionality.

## Core Functionality

The Mimic Potion is a creature that visually resembles a potion but exhibits animalistic AI. It primarily functions as a mobile entity that can interact with its environment and potentially the player.

### Key Components and Attributes

Here are the most important components and their attributes that define the Mimic Potion:

*   **`Base` (Inheritance):**
    *   `data/entities/items/pickup/potion.xml`: Provides foundational potion-like properties, such as physics and material handling.
    *   `data/entities/base_enemy_flying.xml`: Grants it enemy-like AI, movement capabilities, and collision behaviors.

*   **`PhysicsBodyComponent`:**
    *   `is_bullet="1"`: Allows it to be treated as a projectile in some contexts.
    *   `angular_damping="4.5"`: Controls how quickly its rotation slows down.
    *   `hax_fix_going_through_ground="1"`: A specific fix to prevent it from clipping through terrain.

*   **`MaterialInventoryComponent`:**
    *   `on_death_spill="1"`: Ensures its contents are spilled upon death.
    *   `death_throw_particle_velocity_coeff="0.2"`: Controls the velocity of particles when it spills.
    *   `Material material="mimic_liquid" count="1000"`: Defines the primary material it contains and spills.

*   **`DamageModelComponent`:**
    *   `hp="1"`: The Mimic Potion has very low health.
    *   `fire_damage_amount="0.2"`: It can take fire damage.
    *   `materials_that_damage="lava"`: Specifies materials that can damage it.

*   **`MaterialSuckerComponent`:**
    *   `suck_tag="[mimic_liquid]"`: It can suck up specific materials.
    *   `randomized_position`: Defines the area where it can suck materials from.

*   **`AnimalAIComponent`:**
    *   `escape_if_damaged_probability="35"`: Has a chance to flee when damaged.
    *   `creature_detection_range_x="250"`, `creature_detection_range_y="250"`: Defines its sensory range for detecting other creatures.
    *   `sense_creatures="1"`: Enables creature sensing.

*   **`PathFindingComponent`:**
    *   `can_fly="0"`: Despite inheriting from `base_enemy_flying.xml`, it cannot fly.
    *   `can_swim_on_surface="1"`, `can_dive="1"`, `can_walk="1"`, `can_jump="1"`: Defines its movement capabilities.
    *   `jump_trajectories`: A list of predefined jump paths it can take.

*   **`CharacterDataComponent`:**
    *   `platforming_type="0"`: Crucial for correct platforming behavior.
    *   `collision_aabb_min_x/max_x/min_y/max_y`: Defines its collision bounding box.

*   **`GenomeDataComponent`:**
    *   `herd_id="ghost"`: Assigns it to a specific herd group.
    *   `food_chain_rank="7"`: Its position in the food chain.

*   **`AudioComponent`:**
    *   `file="data/audio/Desktop/animals.bank"`: Specifies the audio bank.
    *   `event_root="animals/mimic_potion"`: The root event for its sounds.

*   **`LuaComponent` (Primary AI Script):**
    *   `script_source_file="data/scripts/animals/mimic_potion.lua"`: The main script controlling its behavior.
    *   `execute_on_added="1"`: The script runs when the entity is added.
    *   `execute_every_n_frame="30"`: The script executes periodically.

*   **`SpriteComponent` (Visuals):**
    *   `image_file="data/enemies_gfx/mimic_potion.xml"`: Defines its visual appearance.
    *   `offset_x="4"`, `offset_y="4"`: Adjusts the sprite's position.

*   **`Entity` (Limb Attachments):**
    *   Multiple `<Entity><Base file="data/entities/animals/lukki/lukki_feet/lukki_limb_tiny_dark_animated.xml" /></Entity>`: Attaches small, dark, animated limbs, giving it a creature-like form.

### Removed/Modified Base Components

Several components are explicitly removed or modified from the base entities to tailor the Mimic Potion's behavior:

*   `PhysicsBodyCollisionDamageComponent`: Removed to prevent it from taking damage from collisions.
*   `LuaComponent` (for potion scripts): Removed to prevent standard potion behaviors.
*   `ProjectileComponent`: Removed to prevent projectile-like actions.
*   `SpriteParticleEmitterComponent`: Removed to prevent default potion particles.
*   `ItemComponent`: Disabled to prevent it from being treated as a standard item.
*   `ItemChestComponent`: Disabled to prevent it from dropping items.
*   `ControlsComponent`: Disabled as it's not player-controlled.
*   `CameraBoundComponent`: Removed to prevent camera-specific behaviors.
*   `VelocityComponent`: Removed to manage velocity through other components.
*   `DamageModelComponent` (from base enemy): Removed to avoid duplicate damage handling.

This configuration results in a unique entity that combines potion aesthetics with creature AI, capable of movement, environmental interaction, and a distinct set of behaviors defined by its custom Lua script.