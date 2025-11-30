---
title: Lightning Extra Arcs Projectile
category: entities
---

# Lightning Extra Arcs Projectile

This document details the configuration for the "lightning_extra_arcs" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is based on a default projectile entity with specific modifications for its lightning behavior.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

### Base Projectile Settings

The projectile inherits from `base_projectile.xml`.

```xml
	<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent apply_terminal_velocity="0" >
    </VelocityComponent>
	</Base>
```

*   **`apply_terminal_velocity`**: Set to `0`, meaning the projectile does not adhere to a terminal velocity.

### Projectile Component

This component defines the fundamental properties of the projectile.

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
	<damage_by_type electricity="1.0" >
    </damage_by_type>
  </ProjectileComponent>
```

**Key Attributes:**

*   **`lifetime`**: The projectile exists for `2` seconds.
*   **`projectile_type`**: Set to `LIGHTNING`, indicating its electrical nature.
*   **`muzzle_flash_file`**: Uses `muzzle_flash_laser.xml` for its muzzle effect.
*   **`damage`**: Base damage is `0`.
*   **`shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Defines the RGB color of the light flash when shot (light blue).
*   **`shoot_light_flash_radius`**: The radius of the light flash is `208`.
*   **`damage_by_type electricity`**: Deals `1.0` damage of type `electricity`.

### Lightning Component

This component specifically handles the lightning-related effects and behavior.

```xml
  <LightningComponent
    is_projectile="1"
    explosion_type="1"
    >
    <config_explosion
      never_cache="1"
      camera_shake="7.5"
      explosion_radius="35"
      explosion_sprite="data/particles/explosion_040_electric.xml"
      load_this_entity="data/entities/particles/particle_explosion/main_blue.xml,data/entities/misc/electricity.xml"
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

**Key Attributes within `config_explosion`:**

*   **`camera_shake`**: `7.5` units of camera shake on explosion.
*   **`explosion_radius`**: The explosion covers a radius of `35`.
*   **`explosion_sprite`**: Uses `explosion_040_electric.xml` for the explosion visual.
*   **`load_this_entity`**: Loads `main_blue.xml` and `electricity.xml` particle effects.
*   **`spark_material`**: Uses `spark_electric` for sparks.
*   **`hole_enabled`**: Creates holes (`1`).
*   **`damage_mortals`**: Damages living entities (`1`).
*   **`physics_explosion_power.max`**: Maximum physics force applied by the explosion is `2.5`.
*   **`sparks_enabled`**: Sparks are enabled (`1`).
*   **`stains_enabled`**: Creates stains (`1`) with a radius of `8`.

### Audio Component

Defines the sound associated with the projectile.

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/bullet_lightning">
  </AudioComponent>
```

*   **`file`**: Uses the `projectiles.bank` audio file.
*   **`event_root`**: The specific sound event is `player_projectiles/bullet_lightning`.

### Variable Storage Component

Stores the projectile's own file path.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/lightning_extra_arcs.xml"
		>
	</VariableStorageComponent>
```