---
title: Weak Lightning Projectile
category: entities
---

# Weak Lightning Projectile

This document details the configuration for a weak lightning projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is a projectile with player-originating properties.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

## Base Projectile Configuration

Inherits fundamental projectile behavior.

```xml
	<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent apply_terminal_velocity="0" >
    </VelocityComponent>
	</Base>
```

### Key Attributes:

*   **`apply_terminal_velocity`**: Set to `0`, meaning the projectile does not adhere to terminal velocity.

## Projectile Component

Defines the specific behavior and properties of the lightning projectile.

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
	<damage_by_type electricity="0.5" >
    </damage_by_type>
  </ProjectileComponent>
```

### Key Attributes:

*   **`lifetime`**: The projectile exists for `2` seconds.
*   **`projectile_type`**: Set to `LIGHTNING`, indicating its electrical nature.
*   **`damage`**: Base damage is `0`.
*   **`damage_by_type electricity`**: Applies `0.5` damage specifically of the `electricity` type upon collision.
*   **`muzzle_flash_file`**: Uses a laser-like muzzle flash particle effect.
*   **`shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`, `shoot_light_flash_radius`**: Defines the color and radius of the light flash when the projectile is fired.

## Lightning Component

Specialized component for lightning projectiles, defining its explosion characteristics.

```xml
  <LightningComponent
    is_projectile="1"
    explosion_type="1"
    >
    <config_explosion
      never_cache="1"
      camera_shake="7.5"
	  damage="1.4"
      explosion_radius="15"
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

### Key Attributes:

*   **`is_projectile`**: Set to `1`, indicating this is a projectile-specific lightning effect.
*   **`explosion_type`**: Set to `1`.
*   **`config_explosion`**:
    *   **`camera_shake`**: `7.5` units of camera shake on explosion.
    *   **`damage`**: `1.4` damage dealt by the explosion.
    *   **`explosion_radius`**: The explosion affects an area of `15` units.
    *   **`explosion_sprite`**: Uses `data/particles/explosion_040_electric.xml` for the explosion visual.
    *   **`load_this_entity`**: Loads `data/entities/particles/particle_explosion/main_blue.xml` for explosion effects.
    *   **`spark_material`**: Uses `spark_electric` for sparks.
    *   **`hole_enabled`**: `1`, creates holes upon explosion.
    *   **`hole_image`**: Uses `data/temp/explosion_hole.png` for the hole texture.
    *   **`damage_mortals`**: `1`, the explosion damages living entities.
    *   **`physics_explosion_power.max`**: Maximum physics force applied by the explosion is `2.5`.
    *   **`sparks_count_min`, `sparks_count_max`**: Generates between `1` and `10` sparks.
    *   **`stains_enabled`**: `1`, leaves stains on surfaces.
    *   **`stains_radius`**: Stains have a radius of `8` units.
    *   **`audio_enabled`**: `0`, no specific explosion sound is played by this component.

## Audio Component

Defines the sound played when the projectile is fired.

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/bullet_lightning">
  </AudioComponent>
```

### Key Attributes:

*   **`file`**: Points to the audio bank `data/audio/Desktop/projectiles.bank`.
*   **`event_root`**: Specifies the sound event `player_projectiles/bullet_lightning`.

## Variable Storage Component

Stores the path to this projectile's entity file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/lightning_weak.xml"
		>
	</VariableStorageComponent>
```

### Key Attributes:

*   **`name`**: `projectile_file`.
*   **`value_string`**: The path to this entity file.