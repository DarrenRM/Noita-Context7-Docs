---
title: Bounce Lightning Projectile
category: entities
---

# Bounce Lightning Projectile

This document details the configuration for the "bounce_lightning.xml" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is a player projectile with the tag `projectile_player`.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

## Base Projectile Configuration

Inherits from the default projectile behavior.

```xml
	<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent apply_terminal_velocity="0" >
    </VelocityComponent>
	</Base>
```

## Projectile Component

Defines the projectile's behavior and properties.

### Key Attributes:

*   **`lifetime`**: `2` - The duration the projectile exists before expiring.
*   **`projectile_type`**: `LIGHTNING` - Specifies the projectile's elemental type.
*   **`damage`**: `0` - Base damage of the projectile.
*   **`shoot_light_flash_radius`**: `208` - The radius of the light flash when the projectile is fired.
*   **`damage_by_type`**:
    *   `electricity`: `0.8` - The amount of electrical damage dealt.

```xml
  <ProjectileComponent
    on_collision_die="0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="0"
    lifetime="2"
    projectile_type="LIGHTNING"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_laser.xml"
    damage="0"
    shoot_light_flash_r="190"
    shoot_light_flash_g="248"
    shoot_light_flash_b="255"
    shoot_light_flash_radius="208"
    >
	<damage_by_type electricity="0.8" >
    </damage_by_type>
  </ProjectileComponent>
```

## Lightning Component

Specific configuration for lightning projectiles.

### Key Attributes:

*   **`is_projectile`**: `1` - Indicates this is a projectile.
*   **`explosion_type`**: `1` - Defines the type of explosion.

#### `config_explosion` Sub-element:

This defines the properties of the explosion that occurs upon collision or death.

*   **`camera_shake`**: `7.5` - The intensity of camera shake on explosion.
*   **`explosion_radius`**: `25` - The radius of the explosion.
*   **`damage`**: `3` - The damage dealt by the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_040_electric.xml` - The visual effect for the explosion.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_blue.xml` - The entity to load for the explosion effect.
*   **`hole_enabled`**: `1` - Whether the explosion creates holes.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the hole.
*   **`particle_effect`**: `1` - Enables particle effects for the explosion.
*   **`damage_mortals`**: `1` - Whether the explosion damages living entities.
*   **`physics_explosion_power.max`**: `2.5` - The maximum physics force applied by the explosion.
*   **`sparks_enabled`**: `1` - Enables sparks on explosion.
*   **`sparks_count_max`**: `10` - The maximum number of sparks generated.
*   **`stains_enabled`**: `1` - Enables stains on surfaces from the explosion.
*   **`stains_radius`**: `8` - The radius of the stains.

```xml
  <LightningComponent
    is_projectile="1"
    explosion_type="1"
    >
    <config_explosion
      never_cache="1"
      camera_shake="7.5"
      explosion_radius="25"
	  damage="3"
      explosion_sprite="data/particles/explosion_040_electric.xml"
      load_this_entity="data/entities/particles/particle_explosion/main_blue.xml"
      explosion_sprite_lifetime="0"
      create_cell_probability="1"
      explosion_sprite_emissive="1"
      explosion_sprite_additive="1"
      hole_destroy_liquid="0"
      particle_effect="0"
      spark_material="spark_electric"
      hole_enabled="1"
      hole_image="data/temp/explosion_hole.png"
      particle_effect="1"
      damage_mortals="1"
      physics_explosion_power.max="1.7"
      physics_explosion_power.max="2.5"
      physics_throw_enabled="1"
      shake_vegetation="1"
      sparks_count_min="1"
      sparks_count_max="10"
      sparks_enabled="1"
      stains_enabled="1"
      stains_radius="8"
      audio_enabled="0" >
    </config_explosion>
  </LightningComponent>
```

## Audio Component

Defines the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **`event_root`**: `player_projectiles/bullet_lightning` - The root event for player projectile sounds.

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/bullet_lightning">
  </AudioComponent>
```

## Variable Storage Component

Stores variables related to the projectile.

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/bounce_lightning.xml` - The string value, pointing to the projectile's own file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/bounce_lightning.xml"
		>
	</VariableStorageComponent>
```