---
title: Worm Entity Configuration
category: entities
---

# Worm Entity Configuration

This document details the configuration of the Worm entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Core Entity Properties

The `Entity` tag defines the fundamental properties of the worm.

*   **`name`**: `$animal_worm` - The internal identifier for the worm entity.
*   **`tags`**: A comma-separated list of tags that define the worm's behavior and interactions. Key tags include:
    *   `mortal`: The entity can be killed.
    *   `hittable`: The entity can be damaged by projectiles.
    *   `enemy`: The entity is hostile to the player.
    *   `worm`: Specific tag for worm behavior.
    *   `homing_target`: Can be targeted by homing projectiles.

## Worm Component (`WormComponent`)

This component governs the physical movement and properties of the worm's body segments.

*   **`acceleration`**: `0.5` - How quickly the worm can change its velocity.
*   **`gravity`**: `4` - The gravitational pull affecting the main body.
*   **`tail_gravity`**: `30` - The stronger gravitational pull on the tail segments, causing them to droop.
*   **`part_distance`**: `10` - The desired distance between individual body segments.
*   **`hitbox_radius`**: `5` - The radius of the collision hitbox for each segment.
*   **`target_kill_radius`**: `7` - The radius within which the worm can "kill" or consume a target.
*   **`jump_cam_shake`**: `6` - The intensity of camera shake when the worm jumps.

## Worm AI Component (`WormAIComponent`)

This component controls the worm's artificial intelligence, including movement patterns and target acquisition.

*   **`speed`**: `2` - The base movement speed of the worm.
*   **`speed_hunt`**: `4` - The increased speed when actively hunting a target.
*   **`direction_adjust_speed`**: `0.012` - How quickly the worm adjusts its direction when not hunting.
*   **`direction_adjust_speed_hunt`**: `0.06` - How quickly the worm adjusts its direction when actively hunting.
*   **`hunt_box_radius`**: `256` - The radius around the worm within which it will search for targets to hunt.
*   **`random_target_box_radius`**: `128` - The radius within which the worm will search for random targets to move towards.
*   **`new_hunt_target_check_every`**: `120` - How often (in frames) the AI checks for new hunting targets.
*   **`give_up_time_frames`**: `250` - The number of frames the worm will continue to pursue a target before giving up.

## Damage Model Component (`DamageModelComponent`)

Defines the worm's health, damage resistances, and how it reacts to damage.

*   **`hp`**: `20` - The total hit points of the worm.
*   **`fire_damage_amount`**: `0.2` - The amount of damage taken from fire per tick.
*   **`fire_probability_of_ignition`**: `0.5` - The chance of igniting when hit by fire.
*   **`blood_material`**: `blood_worm` - The material used for blood splatters.
*   **`ragdoll_material`**: `meat_worm` - The material used for the ragdoll when defeated.
*   **`materials_that_damage`**: `acid` - Specifies materials that inflict damage on contact.
*   **`materials_how_much_damage`**: `0.1` - The damage multiplier for materials that inflict damage.
*   **`damage_multipliers`**:
    *   **`drill`**: `0.4` - Reduces damage taken from drills.

## Sprite Components (`SpriteComponent`)

These components define the visual appearance of the worm, including its head, body, and tail. Each `SpriteComponent` typically references a specific graphical asset and animation.

*   **Head Sprite**: `image_file="data/enemies_gfx/worm_head.xml"`
*   **Body Sprites**: `image_file="data/enemies_gfx/worm_body.xml"` (multiple instances for length)
*   **Tail Sprite**: `image_file="data/enemies_gfx/worm_tail.xml"`
*   **`rect_animation`**: `eat` or `stand` - Specifies the animation to play.
*   **`z_index`**: Controls the layering of sprites, with lower values appearing behind higher values.

## Audio Components (`AudioComponent`, `AudioLoopComponent`)

These components manage the sound effects and music associated with the worm.

*   **`AudioComponent` (general)**:
    *   `file`: `data/audio/Desktop/animals.bank` - The audio bank containing the sounds.
    *   `event_root`: `animals` - The root event for general animal sounds.
*   **`AudioComponent` (worm-specific)**:
    *   `event_root`: `animals/worm` - Specific sound events for the worm.
*   **`AudioLoopComponent`**:
    *   `event_name`: `animals/worm/movement_loop` - The sound event for the worm's movement.
    *   `auto_play`: `1` - The sound will play automatically when the entity spawns.

## Other Notable Components

*   **`CellEaterComponent`**: `radius="6"` - Indicates the worm can consume smaller entities within this radius.
*   **`PathFindingGridMarkerComponent`**: Used for navigation pathfinding.
*   **`GenomeDataComponent`**:
    *   `herd_id`: `worm` - Identifies the worm's group for AI interactions.
    *   `food_chain_rank`: `6` - Its position in the in-game food chain.
    *   `is_predator`: `1` - Marks the worm as a predator.
*   **`SpriteStainsComponent`**: Defines how stains appear on the worm's sprites.
*   **`StatusEffectDataComponent`**: Placeholder for status effect data.
*   **`CameraBoundComponent`**: Controls how the camera behaves relative to the worm.
*   **`ItemChestComponent`**: `level="2"`, `enemy_drop="1"` - Indicates the worm can drop loot of a certain rarity.
*   **`MusicEnergyAffectorComponent`**: `energy_target="1"` - Affects music energy.