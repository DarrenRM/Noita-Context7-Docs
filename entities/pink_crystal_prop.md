---
title: Pink Crystal Prop
category: entities
---

# Pink Crystal Prop

This document details the configuration for a pink crystal prop entity in Noita, designed for AI-assisted modding.

## Entity Configuration

The core of the entity is defined by its `Entity` tag, with the `mortal` tag indicating it can be destroyed.

```xml
<Entity tags="mortal" >
	<!-- ... -->
</Entity>
```

## Base Properties

The crystal inherits its fundamental behavior from `base_prop_crystal.xml`.

```xml
<Base file="data/entities/base_prop_crystal.xml" >
	<!-- ... -->
</Base>
```

### Physics and Visuals

The `PhysicsImageShapeComponent` defines the physical shape and visual representation of the crystal.

*   **`image_file`**: Specifies the texture used for the crystal.
    *   `data/props_gfx/crystal_pink.png`
*   **`material`**: The physical material type.
    *   `crystal_solid`

```xml
<PhysicsImageShapeComponent
	image_file="data/props_gfx/crystal_pink.png"
	material="crystal_solid" >
</PhysicsImageShapeComponent>
```

### Material Inventory

The `MaterialInventoryComponent` dictates the materials contained within the crystal.

*   **`count_per_material_type`**: Defines the quantity of specific materials.
    *   `Material material="plasma_fading_pink" count="300"`: The crystal contains 300 units of `plasma_fading_pink`.

```xml
<MaterialInventoryComponent >
	<count_per_material_type>
		<Material material="plasma_fading_pink" count="300"  />
	</count_per_material_type>
</MaterialInventoryComponent>
```

### Damage and Destruction

The `DamageModelComponent` and `ExplodeOnDamageComponent` handle how the crystal reacts to damage.

*   **`DamageModelComponent`**:
    *   `blood_material`: The material that is released upon taking damage.
        *   `plasma_fading_pink`
*   **`ExplodeOnDamageComponent`**:
    *   `config_explosion`: Specifies the entity to spawn upon destruction.
        *   `load_this_entity="data/entities/particles/particle_explosion/main_swirly_pink.xml"`: A pink swirly particle explosion.

```xml
<DamageModelComponent
	blood_material="plasma_fading_pink" >
</DamageModelComponent>

<ExplodeOnDamageComponent>
	<config_explosion
		load_this_entity="data/entities/particles/particle_explosion/main_swirly_pink.xml" >
	</config_explosion>
</ExplodeOnDamageComponent>
```

### Particle Emission

The `ParticleEmitterComponent` controls the particles emitted by the crystal.

*   **`emitted_material_name`**: The material of the emitted particles.
    *   `plasma_fading_pink`

```xml
<ParticleEmitterComponent
	emitted_material_name="plasma_fading_pink" >
</ParticleEmitterComponent>
```

### Lighting

The `LightComponent` adds a light source to the crystal.

*   **`r`, `g`, `b`**: RGB values for the light color.
    *   `r="255"`
    *   `g="20"`
    *   `b="255"`: A pinkish-purple light.

```xml
<LightComponent
	r="255"
	g="20"
	b="255" >
</LightComponent>
```

## Scripted Behavior

The `LuaComponent` attaches custom scripts to the entity.

*   **`script_death`**: The script executed when the entity is destroyed.
    *   `data/scripts/props/crystal_pink_death.lua`
*   **`execute_every_n_frame`**: Set to `-1`, indicating the script is not executed on a frame-by-frame basis but rather triggered by events (like death).

```xml
<LuaComponent
	script_death="data/scripts/props/crystal_pink_death.lua"
	execute_every_n_frame="-1" >
</LuaComponent>
```