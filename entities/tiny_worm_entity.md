---
title: Tiny Worm Entity
category: entities
---

---

# Tiny Worm Entity

This document details the configuration of the "Tiny Worm" entity in Noita, focusing on its attributes and components relevant to AI-assisted modding.

## Core Attributes

The `Entity` tag defines the fundamental properties of the Tiny Worm.

```xml
<Entity
  tags="mortal,hittable,teleportable_NOT,homing_target,enemy,worm,glue_NOT"
  name="$animal_worm_tiny"
>
  <!-- ... other components ... -->
</Entity>
```

*   **`tags`**: A comma-separated list of keywords that define the entity's behavior and interactions. Key tags include:
    *   `mortal`: Can be killed.
    *   `hittable`: Can be damaged by projectiles.
    *   `homing_target`: Can be targeted by homing effects.
    *   `enemy`: Identifies it as a hostile creature.
    *   `worm`: Indicates it's a type of worm.
    *   `teleportable_NOT`: Cannot be teleported.
    *   `glue_NOT`: Cannot be affected by glue.
*   **`name`**: The internal name of the entity, often referencing a localization string (e.g., `$animal_worm_tiny`).

## Worm Component

This component governs the physical and movement characteristics of the worm's body segments.

```xml
<WormComponent
  acceleration="0.3"
  gravity="4"
  tail_gravity="30"
  part_distance="6"
  ground_check_offset="1"
  hitbox_radius="2"
  bite_damage="0.3"
  target_kill_radius="7"
  target_kill_ragdoll_force="8"
  ragdoll_filename="data/ragdolls/worm_tiny/filenames.txt"
  eat_anim_wait_mult="0.05"
  jump_cam_shake="0"
>
</WormComponent>
```

*   **`acceleration`**: How quickly the worm speeds up.
*   **`gravity`**: The gravitational pull affecting the worm's body.
*   **`tail_gravity`**: A stronger gravitational pull specifically for the tail segments, influencing its droop.
*   **`part_distance`**: The ideal distance between consecutive body segments.
*   **`hitbox_radius`**: The radius of the collision box for each segment.
*   **`bite_damage`**: The amount of damage dealt by the worm's bite.
*   **`target_kill_radius`**: The radius within which the worm can instantly kill a target.
*   **`ragdoll_filename`**: Specifies the file containing the ragdoll definitions for the worm.

## Worm AI Component

This component controls the artificial intelligence and movement patterns of the Tiny Worm.

```xml
<WormAIComponent
  speed="2"
  speed_hunt="3"
  direction_adjust_speed="0.010"
  direction_adjust_speed_hunt="0.04"
  hunt_box_radius="256"
  random_target_box_radius="128"
  new_hunt_target_check_every="120"
  new_random_target_check_every="120"
  give_up_area_radius="60"
  give_up_time_frames="250"
>
</WormAIComponent>
```

*   **`speed`**: The base movement speed of the worm.
*   **`speed_hunt`**: The increased speed when actively hunting a target.
*   **`direction_adjust_speed`**: How quickly the worm adjusts its direction when not hunting.
*   **`direction_adjust_speed_hunt`**: How quickly the worm adjusts its direction when actively hunting.
*   **`hunt_box_radius`**: The radius around the worm within which it will actively seek targets.
*   **`random_target_box_radius`**: The radius within which the worm will seek random points to move towards when not hunting.
*   **`give_up_area_radius`**: The radius within which the worm will give up pursuing a target if it moves too far away.
*   **`give_up_time_frames`**: The duration (in frames) the worm will continue to search for a lost target before giving up.

## Cell Eater Component

This component allows the worm to consume "cells" (likely referring to certain materials or entities) in its vicinity.

```xml
<CellEaterComponent
  _tags="cell_eater"
  radius="3"
  only_stain="1"
>
</CellEaterComponent>
```

*   **`radius`**: The area around the worm where it can consume cells.
*   **`only_stain`**: If set to `1`, it suggests this component primarily affects visual stains rather than direct entity consumption.

## Damage Model Component

Defines the health, damage resistances, and how the worm reacts to damage.

```xml
<DamageModelComponent
  _enabled="1"
  air_needed="0"
  falling_damages="0"
  fire_damage_amount="0.2"
  fire_probability_of_ignition="0.5"
  hp="3"
  blood_material="blood_worm"
  blood_spray_material="blood_worm"
  materials_damage="1"
  materials_how_much_damage="0.1"
  materials_that_damage="acid"
  ragdoll_material="meat_worm"
  ragdoll_offset_y="-6"
  blood_sprite_directional="data/particles/bloodsplatters/bloodsplatter_directional_yellow_$[1-3].xml"
  blood_sprite_large="data/particles/bloodsplatters/bloodsplatter_yellow_$[1-3].xml"
>
  <damage_multipliers
    drill="0.4"
  >
  </damage_multipliers>
</DamageModelComponent>
```

*   **`hp`**: The hit points of the Tiny Worm.
*   **`fire_damage_amount`**: The damage dealt by fire per tick.
*   **`fire_probability_of_ignition`**: The chance of igniting when exposed to fire.
*   **`blood_material`**: The material used for blood splatters.
*   **`materials_that_damage`**: Specifies materials that inflict damage to the worm (e.g., "acid").
*   **`materials_how_much_damage`**: The amount of damage taken from specified materials.
*   **`damage_multipliers`**: Modifiers for damage taken from specific sources (e.g., `drill`).

## Sprite Components

These components define the visual appearance of the Tiny Worm, including its head, body segments, and tail.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/enemies_gfx/worm_tiny_head.xml"
  rect_animation="eat"
  next_rect_animation="eat"
  offset_x="9"
  offset_y="4.5"
  z_index="-4.0"
>
</SpriteComponent>

<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/enemies_gfx/worm_tiny_body.xml"
  rect_animation="stand"
  next_rect_animation="stand"
  offset_x="9"
  offset_y="4.5"
  z_index="-3.9"
>
</SpriteComponent>
<!-- ... multiple body segments ... -->
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/enemies_gfx/worm_tiny_tail.xml"
  rect_animation="stand"
  next_rect_animation="stand"
  offset_x="9"
  offset_y="4.5"
  z_index="-3.4"
>
</SpriteComponent>
```

*   **`image_file`**: Path to the sprite's image data.
*   **`rect_animation`**: The current animation state.
*   **`next_rect_animation`**: The animation to transition to.
*   **`offset_x`**, **`offset_y`**: Adjustments to the sprite's position relative to its entity origin.
*   **`z_index`**: Controls the rendering order of sprites. Lower values are rendered behind higher values.

## Sprite Stains Component

These components enable the rendering of stains on the worm's body segments.

```xml
<SpriteStainsComponent
  fade_stains_towards_srite_top="0"
  sprite_id="0">
</SpriteStainsComponent>
<!-- ... for each sprite segment ... -->
```

*   **`sprite_id`**: Links the stain component to a specific `SpriteComponent` by its index.
*   **`fade_stains_towards_srite_top`**: Controls how stains fade along the sprite's vertical axis.

## Audio Components

These components manage the sound effects and music associated with the Tiny Worm.

```xml
<AudioComponent
  file="data/audio/Desktop/animals.bank"
  event_root="animals">
</AudioComponent>

<AudioComponent
  file="data/audio/Desktop/animals.bank"
  event_root="animals/worm">
</AudioComponent>

<AudioLoopComponent
  file="data/audio/Desktop/animals.bank"
  event_name="animals/worm/movement_loop_small"
  set_speed_parameter="1"
  auto_play="1">
</AudioLoopComponent>
```

*   **`file`**: The FMOD audio bank file.
*   **`event_root`**: The base directory for audio events.
*   **`event_name`**: The specific sound event to play.
*   **`auto_play`**: If `1`, the sound will play automatically when the entity spawns.
*   **`set_speed_parameter`**: If `1`, the sound's playback speed will be linked to the entity's movement speed.