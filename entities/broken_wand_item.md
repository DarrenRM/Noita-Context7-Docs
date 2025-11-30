---
title: Broken Wand Item
category: entities
---

# Broken Wand Item

This document details the configuration for the "Broken Wand" item in Noita, focusing on its properties and behaviors relevant to AI-assisted modding.

## Core Entity Configuration

The `BrokenWand` entity is a pickup item with physics properties, designed to be throwable and interactable within the game world.

```xml
<Entity tags="hittable,teleportable_NOT,item_physics,forgeable,broken_wand,item_pickup" >
	<Base file="data/entities/base_item_projectile.xml" />
    <!-- ... other components ... -->
</Entity>
```

### Key Tags:

*   `hittable`: Can be damaged by projectiles.
*   `item_physics`: Behaves like a physics object.
*   `item_pickup`: Can be picked up by the player.
*   `broken_wand`: Specific identifier for this item type.

## Physics and Visuals

This section describes how the broken wand physically exists in the world and its visual representation.

### PhysicsBodyComponent

Manages the physical properties of the wand in the game world.

*   `allow_sleep`: `1` (Allows the object to enter a sleep state when not in motion).
*   `angular_damping`: `0.6` (Reduces rotational velocity over time).
*   `linear_damping`: `0` (No linear damping applied).
*   `fixed_rotation`: `0` (Allows rotation).
*   `is_bullet`: `1` (Treats the object as a projectile for collision purposes).
*   `hax_fix_going_through_ground`: `1` (A fix to prevent it from falling through the ground).

### PhysicsImageShapeComponent

Defines the visual shape and collision bounds using an image.

*   `image_file`: `"data/items_gfx/broken_wand.png"` (The sprite used for the wand's appearance).
*   `material`: `"item_box2d"` (Physics material type).

### PhysicsThrowableComponent

Enables the wand to be thrown by the player.

*   `max_throw_speed`: `180`
*   `throw_force_coeff`: `1.25`
*   `min_torque`: `4`
*   `max_torque`: `10`

### SpriteComponent (in hand)

Defines the visual when the item is held by the player.

*   `image_file`: `"data/items_gfx/broken_wand.png"`
*   `offset_x`, `offset_y`: `4` (Adjusts positioning when held).

## Spell Functionality

The broken wand has unique mechanics related to casting spells, managed by Lua scripts.

### VariableStorageComponent

Stores internal state for the wand's spellcasting.

*   `name="spells_remaining"`: `value_int="0"` (Indicates no spells are currently loaded or available).
*   `name="throw_time"`: `value_int="0"` (Likely related to cooldown or timing for throwing).

### LuaComponent (Scripting)

These components execute custom Lua scripts to define the wand's behavior.

*   **Script for spell handling:**
    *   `script_source_file="data/scripts/items/broken_wand_spells.lua"`
    *   `execute_every_n_frame="12"` (Executes the spell logic periodically).
*   **Script for throwing behavior:**
    *   `script_throw_item="data/scripts/items/broken_wand_throw.lua"`
    *   `execute_every_n_frame="-1"` (Indicates this script is triggered by specific events, likely throwing).

## Item Properties

Standard properties defining the item's identity and interaction.

### ItemComponent

Defines the item's name, pick-up behavior, and inventory placement.

*   `item_name="$item_broken_wand"` (Localized name).
*   `is_pickable`: `1` (Can be picked up).
*   `is_equipable_forced`: `1` (Can be equipped, likely as a wand).
*   `ui_sprite`: `"data/ui_gfx/items/broken_wand.png"` (Icon for UI elements).
*   `ui_description="$item_description_broken_wand"` (Localized description).
*   `preferred_inventory`: `"QUICK"` (Default inventory slot).

### UIInfoComponent

Provides information for UI displays.

*   `name="$item_broken_wand"`

## Visual Effects (FX)

Components that add visual flair to the broken wand.

### LightComponent

Adds a dynamic light source when the wand is active.

*   `radius`: `70`
*   `r`, `g`, `b`: `255`, `94`, `244` (Pinkish-purple color).
*   `blinking_freq`: `0.95` (Controls blinking speed).

### SpriteParticleEmitterComponent (World/Hand)

Emits particles for visual effects.

*   **World/In-Hand Effects:**
    *   `sprite_file`: `"data/particles/ray.xml"` or `"data/particles/spark_electric.xml"`
    *   Various parameters control emission rate, lifetime, color, velocity, and randomization, creating effects like sparks and rays.

### ParticleEmitterComponent (World/Hand)

Another particle emitter for visual effects, often used for more dynamic or cosmetic particles.

*   `emitted_material_name`: `"spark_electric"`
*   Parameters control particle count, lifetime, velocity, and emission patterns.

## Ability Component

Defines special abilities associated with the item.

### AbilityComponent

*   `ui_name="$item_broken_wand"`
*   `throw_as_item`: `1` (Confirms it can be thrown as an item).
*   `gun_config`: `deck_capacity="0"` (Indicates it has no spell deck capacity, fitting its "broken" nature).