---
title: Pink Super Orb Projectile
category: entities
---

---

# Pink Super Orb Projectile

This document details the configuration for the "Pink Super Orb" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity definition for the Pink Super Orb.

```xml
<Entity 
	name="$projectile_default"
	tags="resist_repulsion"
	>
```

### Key Attributes:

*   `name`: `$projectile_default` - Inherits default projectile properties.
*   `tags`: `resist_repulsion` - Indicates resistance to repulsion forces.

## Base Projectile Properties

Inherits fundamental projectile behavior from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
	<VelocityComponent
		gravity_y="0"
		air_friction="0"
		mass="0.05"
		>
	</VelocityComponent> 
</Base>
```

### Key Attributes:

*   `VelocityComponent`:
    *   `gravity_y="0"`: No vertical gravity applied.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.05"`: Low mass, affecting its interaction with physics.

## Projectile Component

Defines the specific behavior and characteristics of the Pink Super Orb.

```xml
<ProjectileComponent 
	_enabled="1" 
	lob_min="0.8"
	lob_max="1.0"
	speed_min="160"
	speed_max="200"
	die_on_low_velocity="0"
	on_death_explode="1"
	on_death_gfx_leave_sprite="0" 
	on_lifetime_out_explode="1"
	explosion_dont_damage_shooter="1"
	damage="1.9"
	go_through_this_material="crystal_purple"
	on_collision_die="1"
	lifetime="50"
	knockback_force="1.0"
	>
	<!-- ... explosion config ... -->
</ProjectileComponent>
```

### Key Attributes:

*   `lob_min`/`lob_max`: `0.8` to `1.0` - Controls the projectile's lobbing behavior.
*   `speed_min`/`speed_max`: `160` to `200` - Sets the projectile's velocity range.
*   `die_on_low_velocity`: `0` - Does not die when velocity drops too low.
*   `on_death_explode`: `1` - Explodes upon death.
*   `on_lifetime_out_explode`: `1` - Explodes when its lifetime expires.
*   `explosion_dont_damage_shooter`: `1` - The explosion does not harm the entity that fired it.
*   `damage`: `1.9` - The base damage dealt by the projectile.
*   `go_through_this_material`: `crystal_purple` - Can pass through "crystal\_purple" material.
*   `on_collision_die`: `1` - Dies upon collision.
*   `lifetime`: `50` - The projectile exists for 50 frames before expiring.
*   `knockback_force`: `1.0` - Applies a knockback force upon impact.

### Explosion Configuration (`config_explosion`):

Defines the properties of the explosion triggered by the projectile.

```xml
<config_explosion
	never_cache="1" 
	camera_shake="0" 
	explosion_radius="6" 
	explosion_sprite="data/particles/explosion_016_plasma_pink.xml" 
	explosion_sprite_lifetime="0.0" 
	create_cell_probability="0" 
	ray_energy="5000"
	hole_destroy_liquid="1" 
	hole_enabled="1" 
	hole_image="data/temp/explosion_hole.png"
	explosion_sprite_emissive="1"
	explosion_sprite_additive="1"
	particle_effect="0" 
	damage_mortals="0"
	physics_explosion_power.min="0.13" 
	physics_explosion_power.max="0.23" 
	physics_throw_enabled="1" 
	shake_vegetation="1" 
	sparks_enabled="0" 
	light_fade_time="0.8" 
	light_r="15"
	light_g="15"
	light_b="40"
	stains_enabled="0" 
	audio_enabled="0" >
</config_explosion>
```

#### Key Explosion Attributes:

*   `explosion_radius`: `6` - The radius of the explosion.
*   `explosion_sprite`: `data/particles/explosion_016_plasma_pink.xml` - The visual effect for the explosion.
*   `ray_energy`: `5000` - The energy of any associated rays.
*   `hole_destroy_liquid`: `1` - The explosion can destroy liquids.
*   `hole_enabled`: `1` - Creates holes in terrain.
*   `explosion_sprite_emissive`/`additive`: `1` - The explosion sprite is emissive and additive.
*   `physics_explosion_power.min`/`max`: `0.13` to `0.23` - Controls the physics impact of the explosion.
*   `shake_vegetation`: `1` - Shakes vegetation in the explosion radius.
*   `light_r`/`g`/`b`: `15`, `15`, `40` - Defines the color of the light emitted by the explosion.

## Visual Components

### Primary Sprite

The main visual representation of the orb.

```xml
<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/projectiles_gfx/orb_pink.xml" 
	offset_x="6" 
	offset_y="6" 
	rect_animation="spawn" 
	update_transform_rotation="0"
	>
</SpriteComponent>
```

#### Key Attributes:

*   `image_file`: `data/projectiles_gfx/orb_pink.xml` - The sprite sheet for the orb.
*   `offset_x`/`offset_y`: `6` - Offsets the sprite's position.
*   `rect_animation`: `spawn` - Uses the "spawn" animation from the sprite sheet.

### Emissive Sprite

A secondary sprite component that adds an emissive glow.

```xml
<SpriteComponent 
	_enabled="1" 
	alpha="1" 
	image_file="data/projectiles_gfx/orb_pink.xml" 
	offset_x="6" 
	offset_y="6" 
	rect_animation="spawn" 
	emissive="1"
	additive="1"
	update_transform_rotation="0"
	>
</SpriteComponent>
```

#### Key Attributes:

*   `emissive`: `1` - Makes the sprite emit light.
*   `additive`: `1` - Uses additive blending for the sprite.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent 
	_enabled="1" 
	radius="150" 
	r="130"
	g="35"
	b="90">
</LightComponent>
```

### Key Attributes:

*   `radius`: `150` - The radius of the light emitted.
*   `r`/`g`/`b`: `130`, `35`, `90` - Defines the color of the light (pinkish-purple hue).

## Audio Component

Specifies the sound bank and event root for the projectile's audio.

```xml
<AudioComponent
	file="data/audio/Desktop/projectiles.bank"
	event_root="projectiles/orb_c" >
</AudioComponent>
```

### Key Attributes:

*   `file`: `data/audio/Desktop/projectiles.bank` - The Wwise sound bank file.
*   `event_root`: `projectiles/orb_c` - The base event path for projectile sounds.

## Variable Storage Component

Stores a variable related to the projectile's own file path.

```xml
<VariableStorageComponent
	name="projectile_file"
	value_string="data/entities/projectiles/orb_pink_super.xml"
	>
</VariableStorageComponent>
```

### Key Attributes:

*   `name`: `projectile_file` - The name of the variable.
*   `value_string`: `data/entities/projectiles/orb_pink_super.xml` - The string value, pointing to this entity's XML file.