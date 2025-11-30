---
title: Physics Barrel Water
category: entities
---

# Physics Barrel Water

This document describes the `physics_barrel_water.xml` entity, which represents a destructible barrel filled with water in Noita. It's designed for AI-assisted modding, focusing on key attributes for understanding and modification.

## Core Components

The `physics_barrel_water.xml` entity is built upon several core components that define its behavior and properties.

### Base Entity

```xml
<Entity tags="mortal" >
  <Base file="data/entities/base_item_physics2.xml" >
    <PhysicsBody2Component
      kill_entity_after_initialized="0" >
    </PhysicsBody2Component>
    <PhysicsImageShapeComponent
      image_file="data/props_gfx/barrel_water.png"
      material="wood_prop" >
    </PhysicsImageShapeComponent>
  </Base>
  ...
</Entity>
```

*   **`tags="mortal"`**: This tag is crucial as it allows the entity to be affected by damage and potentially explode.
*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits fundamental physics properties from a generic physics object.
*   **`PhysicsBody2Component`**: Manages the physical body of the barrel. `kill_entity_after_initialized="0"` means it won't be immediately removed upon creation.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation and collision shape.
    *   `image_file`: Specifies the sprite for the barrel (`data/props_gfx/barrel_water.png`).
    *   `material="wood_prop"`: Assigns a wood material for physics interactions.

### Material Inventory

```xml
  <MaterialInventoryComponent
    _enabled="1"
    drop_as_item="0"
    on_death_spill="1"
    leak_on_damage_percent="0.999"
    audio_collision_size_modifier_amount="1"
    >
    <count_per_material_type>
      <Material material="water" count="750"  />
    </count_per_material_type>
  </MaterialInventoryComponent>
```

This component manages the liquid contents of the barrel.

*   **`_enabled="1"`**: Ensures the component is active.
*   **`drop_as_item="0"`**: The barrel itself does not drop as an item upon destruction.
*   **`on_death_spill="1"`**: When the entity is destroyed, its contents will spill out.
*   **`leak_on_damage_percent="0.999"`**: The barrel will start leaking when it reaches 99.9% damage.
*   **`count_per_material_type`**: Defines the materials and their quantities inside.
    *   **`Material material="water" count="750"`**: The barrel contains 750 units of water.

### Damage Model

```xml
  <DamageModelComponent
    air_needed="0"
    blood_material="water"
    drop_items_on_death="0"
    falling_damage_damage_max="1.2"
    falling_damage_damage_min="0.1"
    falling_damage_height_max="250"
    falling_damage_height_min="70"
    falling_damages="0"
    fire_damage_amount="0.4"
    fire_probability_of_ignition="0"
	  critical_damage_resistance="1"
    hp="0.3"
    is_on_fire="0"
    materials_create_messages="0"
    materials_damage="1"
    materials_that_damage="fire,lava,acid"
    materials_how_much_damage="0.0002,0.0001,0.001"
    ragdoll_filenames_file=""
    ragdoll_material="" >
	<damage_multipliers
		melee="0.1"
		>
	</damage_multipliers>
  </DamageModelComponent>
```

This component governs how the barrel takes damage and reacts to it.

*   **`air_needed="0"`**: The barrel does not require air to function or be damaged.
*   **`blood_material="water"`**: When damaged, it can spill water.
*   **`falling_damage_...`**: Parameters related to damage taken from falling.
*   **`fire_damage_amount="0.4"`**: Deals 0.4 damage per tick when on fire.
*   **`fire_probability_of_ignition="0"`**: Cannot ignite from fire.
*   **`hp="0.3"`**: Has very low health, making it easily destructible.
*   **`materials_that_damage="fire,lava,acid"`**: Specifies which materials can damage the barrel.
*   **`materials_how_much_damage="0.0002,0.0001,0.001"`**: The amount of damage dealt by the respective materials.
*   **`damage_multipliers`**:
    *   **`melee="0.1"`**: Takes only 10% of damage from melee attacks.

## Audio Components

The barrel has several audio components to provide feedback during interactions.

### Spray Sound

```xml
  <AudioLoopComponent
    _tags="sound_spray"
    file="data/audio/Desktop/materials.bank"
    event_name="materials/spray"
    volume_autofade_speed="0.25" >
  </AudioLoopComponent>
```

*   **`_tags="sound_spray"`**: Associates this sound with spraying effects.
*   **`event_name="materials/spray"`**: Triggers a spray sound event.

### Collision Sounds

```xml
  <AudioComponent
    file="data/audio/Desktop/materials.bank"
    event_root="collision/wood"
    set_latest_event_position="1" >
  </AudioComponent>

  <AudioComponent
    file="data/audio/Desktop/materials.bank"
    event_root="collision/barrel_water" >
  </AudioComponent>

  <AudioComponent
    file="data/audio/Desktop/materials.bank"
    event_root="collision/metalhollow" >
  </AudioComponent>
```

These components play different sounds when the barrel collides with surfaces:

*   **`event_root="collision/wood"`**: A generic wood collision sound.
*   **`event_root="collision/barrel_water"`**: A specific sound for water barrel collisions.
*   **`event_root="collision/metalhollow"`**: A hollow metal collision sound, likely for when the barrel is empty or partially empty.