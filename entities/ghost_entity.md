---
title: Ghost Entity
category: entities
---

# Ghost Entity

This document details the `ghost.xml` entity, providing key attributes for AI-assisted modding.

## Entity Definition

The `ghost` entity is a hostile creature with specific behaviors and resistances.

```xml
<Entity
  name="$animal_ghost"
  tags="mortal,hittable,music_energy_000_near,enemy,glue_NOT"
  serialize="0" >
  <!-- ... other components ... -->
</Entity>
```

### Key Tags:

*   `mortal`: Can be killed.
*   `hittable`: Can be damaged.
*   `enemy`: Hostile to the player.
*   `glue_NOT`: Cannot be glued.

## DamageModelComponent

Defines the health, damage resistances, and death-related behaviors of the ghost.

```xml
<DamageModelComponent
  _enabled="1"
  blood_material="blood_worm"
  blood_spray_material="blood_worm"
  drop_items_on_death="1"
  hp="20"
  max_hp="20"
  ragdoll_material="meat_worm"
  ragdoll_offset_y="-6"
  materials_damage="1"
  materials_how_much_damage="0.1"
  materials_that_damage="acid" >
  <!-- ... damage_multipliers ... -->
</DamageModelComponent>
```

### Key Attributes:

*   `hp`: Current health points (20).
*   `max_hp`: Maximum health points (20).
*   `drop_items_on_death`: Whether it drops items upon death (1 - enabled).
*   `materials_that_damage`: Materials that can damage the ghost (e.g., "acid").
*   `materials_how_much_damage`: The amount of damage dealt by specified materials (0.1).

#### Damage Multipliers:

The ghost has no specific damage multipliers for common damage types.

```xml
<damage_multipliers
  drill="0"
  electricity="0"
  explosion="0"
  fire="0"
  melee="0"
  projectile="0"
  ice="0"
  slice="0"
  holy="0" >
</damage_multipliers>
```

## GenomeDataComponent

Provides information about the ghost's place in the ecosystem.

```xml
<GenomeDataComponent
  _enabled="1"
  food_chain_rank="6"
  herd_id="ghost"
  is_predator="1" >
</GenomeDataComponent>
```

### Key Attributes:

*   `food_chain_rank`: Its position in the food chain (6).
*   `herd_id`: Identifier for its group ("ghost").
*   `is_predator`: Indicates if it's a predator (1 - true).

## DamageNearbyEntitiesComponent

Allows the ghost to damage nearby entities.

```xml
<DamageNearbyEntitiesComponent
  radius="16"
  time_between_damaging="3"
  target_tag="player_unit"
  damage_type="DAMAGE_CURSE"
  ragdoll_fx="NONE">
</DamageNearbyEntitiesComponent>
```

### Key Attributes:

*   `radius`: The area of effect for damage (16 pixels).
*   `time_between_damaging`: Cooldown between damage applications (3 frames).
*   `target_tag`: Entities targeted for damage ("player_unit").
*   `damage_type`: The type of damage dealt ("DAMAGE_CURSE").

## GhostComponent

Defines the unique movement and AI behavior of the ghost.

```xml
<GhostComponent
  _enabled="1"
  hunt_box_radius="412"
  new_hunt_target_check_every="150"
  speed="20"
  velocity.x="-0.37877"
  velocity.y="-0.307411" >
</GhostComponent>
```

### Key Attributes:

*   `hunt_box_radius`: The radius within which the ghost will actively hunt targets (412 pixels).
*   `new_hunt_target_check_every`: How often it checks for new targets (150 frames).
*   `speed`: The movement speed of the ghost (20).
*   `velocity.x`, `velocity.y`: Initial movement vector.

## SpriteComponent

Handles the visual representation of the ghost.

```xml
<SpriteComponent
  _enabled="1"
  additive="1"
  alpha="0.671429"
  emissive="1"
  image_file="data/enemies_gfx/ghost.xml"
  update_transform="1"
  update_transform_rotation="1" >
</SpriteComponent>
```

### Key Attributes:

*   `image_file`: Path to the sprite's graphical definition ("data/enemies_gfx/ghost.xml").
*   `alpha`: Transparency level (0.671429).
*   `emissive`: Whether the sprite emits light (1 - enabled).
*   `additive`: Uses additive blending for rendering (1 - enabled).

## AudioComponent & AudioLoopComponent

Manages the sound effects associated with the ghost.

```xml
<AudioComponent
  file="data/audio/Desktop/animals.bank"
  event_root="animals/ghost" >
</AudioComponent>

<AudioLoopComponent
  file="data/audio/Desktop/animals.bank"
  event_name="animals/ghost/movement_loop"
  set_speed_parameter="1"
  auto_play="1">
</AudioLoopComponent>
```

### Key Attributes:

*   `file`: The audio bank file used.
*   `event_root`: The root event path for general sounds.
*   `event_name`: Specific event for the movement loop.
*   `auto_play`: Whether the loop starts automatically (1 - enabled).
*   `set_speed_parameter`: Links audio speed to entity movement (1 - enabled).