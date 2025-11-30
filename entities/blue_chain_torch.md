---
title: Blue Chain Torch
category: entities
---

# Blue Chain Torch

This document details the configuration for a blue chain torch entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The `chain_torch_blue.xml` file defines a `hittable` entity that inherits its base functionality from `base_chain_torch.xml`.

```xml
<Entity tags="hittable" serialize="1" >
  	<Base file="data/entities/base_chain_torch.xml" /> 
  	<Entity>
        <!-- ... components ... -->
    </Entity>
</Entity>
```

## Key Components

### InheritTransformComponent

This component is used to define the relative position of the torch's visual and functional elements.

```xml
<InheritTransformComponent>
	<Transform 
		position.x="0"
		position.y="0" 
	></Transform>
</InheritTransformComponent>
```

*   **`position.x`**: X-axis offset.
*   **`position.y`**: Y-axis offset.

### LightComponent

This component controls the light emitted by the torch.

```xml
<LightComponent 
	_tags="fire"
	radius="96"
	fade_out_time="1.5"
></LightComponent>
```

*   **`_tags`**: Marks this component as related to "fire".
*   **`radius`**: The visual radius of the light source.
*   **`fade_out_time`**: The duration in seconds for the light to fade out.

### TorchComponent

This component provides the core functionality of a torch.

```xml
<TorchComponent
	fire_audio_weight="0.5"
	suffocation_check_offset_y="-1"
></TorchComponent>
```

*   **`fire_audio_weight`**: Influences the intensity or presence of fire-related audio.
*   **`suffocation_check_offset_y`**: An offset used in checks related to suffocation mechanics.

### SpriteAnimatorComponent

This component is present but empty, suggesting that sprite animations are handled by the base entity or other inherited components.

```xml
<SpriteAnimatorComponent>
</SpriteAnimatorComponent>
```

### Base Torch Particle Configuration

This section inherits from `base_torch_particle.xml` and adds specific particle emitters for the blue torch.

```xml
<Base file="data/entities/base_torch_particle.xml" >
	<ParticleEmitterComponent 
		x_pos_offset_min="-3"
		x_pos_offset_max="2" 
		y_pos_offset_min="0"
		y_pos_offset_max="2"
	></ParticleEmitterComponent>

	<ParticleEmitterComponent 
		color="ff50e7f0"
		emitted_material_name="spark_blue"
		x_pos_offset_min="-3"
		x_pos_offset_max="2"
		y_pos_offset_min="0"
		y_pos_offset_max="2"
	></ParticleEmitterComponent>

	<ParticleEmitterComponent 
		emitted_material_name="spark_blue"
		x_pos_offset_min="-3"
		x_pos_offset_max="2"
		y_pos_offset_min="0"
		y_pos_offset_max="2"
	></ParticleEmitterComponent>
</Base>
```

#### ParticleEmitterComponent Details

*   **`x_pos_offset_min` / `x_pos_offset_max`**: Defines the minimum and maximum X-axis offset for particle emission.
*   **`y_pos_offset_min` / `y_pos_offset_max`**: Defines the minimum and maximum Y-axis offset for particle emission.
*   **`color`**: Specifies the color of the emitted particles (in ARGB hex format). `ff50e7f0` represents a vibrant blue.
*   **`emitted_material_name`**: The name of the material to be emitted as particles. `spark_blue` indicates blue sparks.

This configuration results in a blue torch that emits light and blue sparks.