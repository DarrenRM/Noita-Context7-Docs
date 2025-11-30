---
title: Dark Ghost Entity
category: entities
---

# Dark Ghost Entity

This document details the Dark Ghost entity, a hostile creature found in Noita. It focuses on key attributes relevant for AI-assisted modding.

## Core Entity Properties

The `Entity` tag defines the fundamental properties of the Dark Ghost.

```xml
<Entity
  name="$animal_darkghost"
  tags="mortal,hittable,enemy,glue_NOT"
  serialize="0" >
  <!-- ... other components ... -->
</Entity>
```

*   **`name`**: `$animal_darkghost` - Internal identifier for the entity.
*   **`tags`**:
    *   `mortal`: Can be killed.
    *   `hittable`: Can be damaged.
    *   `enemy`: Hostile towards the player.
    *   `glue_NOT`: Cannot be glued.
*   **`serialize`**: `0` - Indicates this entity is not saved with the game state.

## DamageModelComponent

This component governs how the Dark Ghost takes damage and its resistances.

```xml
<DamageModelComponent
  _enabled="1"
  hp="20"
  max_hp="20"
  falling_damages="0"
  fire_damage_amount="0.2"
  fire_probability_of_ignition="0.5"
  materials_damage="1"
  materials_how_much_damage="0.1"
  materials_that_damage="acid"
  >
  <!-- ... damage multipliers ... -->
</DamageModelComponent>
```

*   **`hp` / `max_hp`**: `20` - The creature's health points.
*   **`falling_damages`**: `0` - Does not take damage from falling.
*   **`fire_damage_amount`**: `0.2` - Base damage from fire.
*   **`fire_probability_of_ignition`**: `0.5` - 50% chance to ignite when hit by fire.
*   **`materials_damage`**: `1` - Can be damaged by certain materials.
*   **`materials_how_much_damage`**: `0.1` - The amount of damage taken from materials.
*   **`materials_that_damage`**: `"acid"` - Specifically damaged by acid.

### Damage Multipliers

This nested tag defines how much extra damage the entity takes from specific damage types.

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
  holy="0"
  >
</damage_multipliers>
```

*   All multipliers are set to `0`, meaning the Dark Ghost takes no bonus damage from any of these sources.

## GenomeDataComponent

This component defines the creature's role within the game's ecosystem.

```xml
<GenomeDataComponent
  _enabled="1"
  food_chain_rank="6"
  herd_id="ghost"
  is_predator="1" >
</GenomeDataComponent>
```

*   **`food_chain_rank`**: `6` - Its position in the food chain.
*   **`herd_id`**: `"ghost"` - Identifies it as part of the "ghost" group.
*   **`is_predator`**: `1` - It actively hunts other creatures.

## DamageNearbyEntitiesComponent

This component allows the Dark Ghost to damage entities within a certain radius.

```xml
<DamageNearbyEntitiesComponent
  radius="16"
  time_between_damaging="3"
  damage_min="0.2"
  damage_max="0.3"
  target_tag="player_unit"
  ragdoll_fx="NONE">
</DamageNearbyEntitiesComponent>
```

*   **`radius`**: `16` - The area of effect for damaging nearby entities.
*   **`time_between_damaging`**: `3` - The cooldown in frames between damage applications.
*   **`damage_min` / `damage_max`**: `0.2` / `0.3` - The range of damage dealt.
*   **`target_tag`**: `"player_unit"` - Only targets the player.

## GhostComponent

This component defines the unique movement and hunting behavior of the Dark Ghost.

```xml
<GhostComponent
  _enabled="1"
  hunt_box_radius="412"
  new_hunt_target_check_every="150"
  speed="30"
  velocity.x="-0.37877"
  velocity.y="-0.307411" >
</GhostComponent>
```

*   **`hunt_box_radius`**: `412` - The large radius within which it will actively hunt targets.
*   **`new_hunt_target_check_every`**: `150` - How often (in frames) it re-evaluates its hunt target.
*   **`speed`**: `30` - The movement speed of the ghost.
*   **`velocity.x` / `velocity.y`**: `-0.37877` / `-0.307411` - Initial movement direction and magnitude.

## SpriteComponent

These components define the visual appearance of the Dark Ghost.

```xml
<SpriteComponent
  _enabled="1"
  additive="1"
  alpha="0.671429"
  emissive="1"
  image_file="data/enemies_gfx/darkghost.xml"
  >
</SpriteComponent>

<SpriteComponent
  _enabled="1"
  image_file="data/enemies_gfx/darkghost_skull.xml"
  >
</SpriteComponent>
```

*   **`image_file`**: Specifies the graphical assets used. The first uses `darkghost.xml` with additive blending and emissive properties for a ghostly effect. The second adds a skull sprite.
*   **`alpha`**: `0.671429` - Controls the transparency of the primary sprite.
*   **`additive` / `emissive`**: `1` - These flags contribute to the ethereal, glowing appearance.

## LuaComponent

This component links the entity to custom Lua scripting for advanced behaviors.

```xml
<LuaComponent
  _enabled="1"
  script_source_file="data/scripts/animals/darkghost.lua"
  execute_every_n_frame="80"
  >
</LuaComponent>
```

*   **`script_source_file`**: `"data/scripts/animals/darkghost.lua"` - The path to the associated Lua script.
*   **`execute_every_n_frame`**: `80` - The script's logic will run approximately every 80 frames.