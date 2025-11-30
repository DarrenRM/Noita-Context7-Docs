---
title: Gravity Field Enemy (Short)
category: entities
---

# Gravity Field Enemy (Short)

This entity defines a short-duration gravity field effect, likely used by enemies to manipulate player movement or projectiles. It primarily utilizes particle emitters to create a visual and functional gravity well.

## Key Components

### LuaComponent

This component links the entity to a Lua script responsible for its behavior.

*   **`script_source_file`**: `data/scripts/projectiles/projectile_gravity_small.lua` - The script that governs the gravity field's logic.
*   **`execute_every_n_frame`**: `1` - The script logic executes every frame.

### ParticleEmitterComponent (x2)

These components are responsible for emitting visual particles that represent the gravity field.

#### Emitter 1 (Inner Field)

*   **`emitted_material_name`**: `spark_purple_bright` - The material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by global gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - Particles exist for a short duration.
*   **`count_min` / `count_max`**: `2` / `4` - A small number of particles are emitted.
*   **`area_circle_radius.max`**: `72` - Defines the maximum radius of the emission area.
*   **`airflow_force`**: `0.5` - Particles are influenced by airflow.
*   **`attractor_force`**: `16` - Particles are attracted towards a central point.

#### Emitter 2 (Outer Field)

*   **`emitted_material_name`**: `spark_purple_bright` - The material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by global gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - Particles exist for a short duration.
*   **`count_min` / `count_max`**: `10` / `20` - A larger number of particles are emitted.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `72` / `72` - The emission area is a precise circle of radius 72.
*   **`airflow_force`**: `0.3` - Particles are influenced by airflow.

### UIIconComponent

This component defines how the gravity field is represented in the UI.

*   **`name`**: `$streamingevent_gravity_player` - The internal name for the UI element.
*   **`description`**: `$streamingeventdesc_gravity_player` - The description text for the UI element.
*   **`icon_sprite_file`**: `data/ui_gfx/status_indicators/gravity_field.png` - The sprite used for the icon.
*   **`display_in_hud`**: `1` - The icon is displayed in the HUD.

### Base (Inherited from `data/entities/projectiles/deck/base_field.xml`)

This entity inherits properties from a base field projectile.

*   **`SpriteComponent`**: Defines the visual appearance of the field indicator.
    *   **`image_file`**: `data/particles/area_indicator_072_purple_dark.png` - The sprite for the field's visual representation.
    *   **`z_index`**: `1.2` - Controls the rendering order.
    *   **`offset_x` / `offset_y`**: `36` / `36` - Offsets the sprite's position.
*   **`LifetimeComponent`**:
    *   **`lifetime`**: `600` - The total duration of the gravity field in frames.
*   **`ProjectileComponent`**:
    *   **`config_explosion`**: Defines explosion properties if the field were to explode.

```xml
<Entity>

	<InheritTransformComponent />
  
	<LuaComponent
		script_source_file="data/scripts/projectiles/projectile_gravity_small.lua"
		execute_every_n_frame="1"
		>
	</LuaComponent>
	
	<ParticleEmitterComponent 
		emitted_material_name="spark_purple_bright"
		gravity.y="0.0"
		lifetime_min="0.5"
		lifetime_max="1.5"
		count_min="2"
		count_max="4"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="72"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		is_emitting="1" 
		draw_as_long="1"
		attractor_force="16"
		>
	</ParticleEmitterComponent>

  	<ParticleEmitterComponent 
		emitted_material_name="spark_purple_bright"
		gravity.y="0.0"
		lifetime_min="0.5"
		lifetime_max="1.5"
		count_min="10"
		count_max="20"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.min="72"
		area_circle_radius.max="72"
		cosmetic_force_create="0"
		airflow_force="0.3"
		airflow_time="0.01"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
	
	<UIIconComponent
		name="$streamingevent_gravity_player"
		description="$streamingeventdesc_gravity_player"
		icon_sprite_file="data/ui_gfx/status_indicators/gravity_field.png"
		is_perk="0"
		display_above_head="0"
		display_in_hud="1"
		>
	</UIIconComponent>
	
	<Base file="data/entities/projectiles/deck/base_field.xml">
		<SpriteComponent 
			image_file="data/particles/area_indicator_072_purple_dark.png"
			z_index="1.2"
			offset_x="36"
			offset_y="36"
			_enabled="0"
			>
		</SpriteComponent>
		
		<LifetimeComponent lifetime="600">
		</LifetimeComponent>

		<SpriteParticleEmitterComponent
			_enabled="0"
			>
		</SpriteParticleEmitterComponent>

		<ProjectileComponent 
			damage_game_effect_entities=""
			>
			<config_explosion
				explosion_sprite="data/particles/blast_out.xml"
				>
			</config_explosion>
		</ProjectileComponent>
	</Base>

</Entity>
```