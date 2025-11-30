---
title: Longleg Enemy Entity
category: entities
---

# Longleg Enemy Entity

This document details the `longleg.xml` entity, defining the behavior and attributes of the Longleg creature in Noita.

## Core Components

The Longleg is a basic enemy with several key components that dictate its functionality.

### Base Enemy Configuration

The `Base` component inherits from `base_enemy_basic.xml`, providing fundamental enemy properties.

*   **ItemChestComponent**: Grants the Longleg a chance to drop items upon defeat. `level="1"` indicates a basic item drop.
*   **AnimalAIComponent**: Manages the creature's artificial intelligence.
    *   `escape_if_damaged_probability="100"`: The Longleg will always attempt to flee when damaged.
    *   `sense_creatures="1"`: The creature can detect other living beings.
    *   `attack_melee_max_distance="10"`: The maximum range for its melee attack.
    *   `attack_dash_enabled="1"`: The Longleg can perform a dash attack.
    *   `eating_area_radius_x="8"`, `eating_area_radius_y="8"`: Defines the area around the creature where it can "eat" or interact with its environment.
    *   `mouth_offset_x="0"`, `mouth_offset_y="6"`: Positions the creature's "mouth" for interactions.
*   **SpriteComponent**: Defines the visual appearance of the Longleg.
    *   `image_file="data/enemies_gfx/longleg.xml"`: Specifies the sprite sheet used for the creature.
    *   `offset_x="6"`, `offset_y="12"`: Adjusts the sprite's position relative to its entity origin.
*   **SpriteAnimatorComponent**: Handles sprite animations.
    *   `rotate_to_surface_normal="0"`: The sprite does not automatically rotate to align with the surface it's on.
*   **DamageModelComponent**: Manages health, damage, and death effects.
    *   `hp="0.11"`: The Longleg has very low health.
    *   `ragdoll_filenames_file="data/ragdolls/longleg/filenames.txt"`: Specifies the files for its ragdoll physics upon death.
    *   `ragdoll_offset_y="-6"`: Adjusts the ragdoll's vertical position.
    *   `blood_sprite_directional`, `blood_sprite_large`: Defines the sprites used for blood splatters.
    *   `blood_spray_material="blood"`: The material used for blood effects.
    *   `blood_spray_create_some_cosmetic="1"`: Enables cosmetic blood effects.
*   **CharacterPlatformingComponent**: Governs movement and jumping.
    *   `jump_velocity_y="-140"`: The vertical force applied when jumping.
    *   `run_velocity="25"`: The creature's horizontal movement speed.
*   **GenomeDataComponent**: Assigns genetic properties, useful for herd behavior.
    *   `herd_id="spider"`: Identifies the Longleg as part of the "spider" herd.
*   **HitboxComponent**: Defines the collision area for interactions and attacks.
    *   `aabb_min_x="-5"`, `aabb_min_y="-6"`, `aabb_max_x="5"`, `aabb_max_y="6"`: The bounding box coordinates.
*   **CharacterDataComponent**: Provides general character physics and collision data.
    *   `collision_aabb_min_x="-2"`, `collision_aabb_max_x="2"`, `collision_aabb_min_y="-6"`, `collision_aabb_max_y="3"`: Defines the precise collision box for character interactions.
    *   `mass="0.4"`: The mass of the character.

### Audio and Interaction

*   **AudioComponent**: Manages sound effects.
    *   `file="data/audio/Desktop/animals.bank"`: The audio bank containing animal sounds.
    *   `event_root="animals/longleg"`: The root event name for Longleg sounds.
*   **InteractableComponent**: Allows the Longleg to be interacted with, particularly when charmed.
    *   `_tags="enabled_in_world,enabled_if_charmed"`: The interaction is active in the world and when the creature is charmed.
    *   `_enabled="0"`: The interaction is disabled by default.
    *   `name="longleg_love"`: The internal name for this interaction.
    *   `ui_text="$ui_longleg_love"`: The text displayed in the UI for this interaction.
    *   `exclusivity_group="1"`: Ensures this interaction doesn't conflict with others.
*   **LuaComponent**: Executes custom Lua scripts.
    *   `script_interacting="data/scripts/animals/longleg_pet.lua"`: A script executed when the `longleg_love` interaction is used.
    *   `script_source_file="data/scripts/animals/longleg_love.lua"`: The main script file for the Longleg's love/charm behavior.
    *   `execute_every_n_frame="60"`: The `longleg_love.lua` script runs every 60 frames.