---
title: Digger Projectile
category: entities
---

# Digger Projectile

This document describes the `digger.xml` entity, which defines a special projectile in Noita. This projectile is designed to dig through terrain and has unique properties related to its impact and destruction.

## Entity Definition

The core of this entity is a projectile with player-originating tags.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

## Projectile Component

This component governs the behavior of the projectile.

### Key Attributes:

*   **`_enabled`**: Controls if the projectile is active.
*   **`lob_min`, `lob_max`**: Defines the minimum and maximum lobbing behavior (arc of the projectile).
*   **`speed_min`, `speed_max`**: Sets the projectile's speed range.
*   **`friction`**: How much the projectile slows down over time.
*   **`on_death_explode`**: If the projectile explodes upon death (e.g., hitting a wall).
*   **`on_lifetime_out_explode`**: If the projectile explodes when its lifetime expires.
*   **`ground_collision_fx`**: Enables visual effects on ground collision.
*   **`explosion_dont_damage_shooter`**: Prevents the projectile's explosion from harming the player who shot it.
*   **`on_collision_die`**: If the projectile is destroyed upon collision.
*   **`lifetime`**: The duration the projectile exists before expiring.
*   **`damage`**: Base damage dealt by the projectile.
*   **`velocity_sets_scale`**: If the projectile's velocity influences its scale.
*   **`camera_shake_when_shot`**: The intensity of camera shake when this projectile is fired.
*   **`ragdoll_fx_on_collision`**: The ragdoll effect triggered on collision.
*   **`collect_materials_to_shooter`**: If the projectile collects materials from its impact point and returns them to the shooter.
*   **`collide_with_tag`**: The entity tags this projectile can collide with.
*   **`shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Properties for a light flash effect when the projectile is shot.

### Damage by Type:

This section specifies how damage is applied to different material types.

| Type  | Value | Description                                   |
| :---- | :---- | :-------------------------------------------- |
| `drill` | 0.3   | Damage specifically applied to drillable terrain. |

### Config Explosion:

Defines the properties of the explosion that occurs when the projectile dies or its lifetime expires.

*   **`never_cache`**: Prevents caching of this explosion for performance.
*   **`camera_shake`**: Intensity of camera shake from the explosion.
*   **`explosion_radius`**: The radius of the explosion.
*   **`hole_enabled`**: If the explosion creates a hole in terrain.
*   **`damage`**: Damage dealt by the explosion.
*   **`ray_energy`**: Energy of rays emitted by the explosion.
*   **`max_durability_to_destroy`**: Maximum durability of terrain that can be destroyed by the explosion.
*   **`hole_image`**: The image used for the explosion hole.
*   **`physics_explosion_power.max`**: Maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: If the explosion can throw physics objects.
*   **`shake_vegetation`**: If the explosion shakes vegetation.
*   **`material_sparks_enabled`**: If material sparks are generated.
*   **`stains_enabled`**: If impact stains are created.
*   **`is_digger`**: Crucially, marks this as a digging projectile.
*   **`audio_enabled`**: If explosion sounds are played.

```xml
<ProjectileComponent 
    _enabled="1" 
    lob_min="0.8"
    lob_max="1.0"
    speed_min="0"
    speed_max="0"
    friction="3.0"
    direction_random_rad="0"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="1"
    ground_collision_fx="1"
    explosion_dont_damage_shooter="1" 
    on_collision_die="1"
    lifetime="2"
    damage="0"
    velocity_sets_scale="1"
    lifetime_randomness="0"
    ragdoll_force_multiplier="0.01"
    hit_particle_force_multiplier="0.25 "
    camera_shake_when_shot="2.0"
    ragdoll_fx_on_collision="BLOOD_SPRAY"
    collect_materials_to_shooter="1"
    collide_with_tag="hittable"
    on_death_item_pickable_radius="10"
	shoot_light_flash_radius="20"
	shoot_light_flash_r="40"
    shoot_light_flash_g="180"
    shoot_light_flash_b="255" >
	<damage_by_type 
		drill="0.3"
		>
    </damage_by_type>
    <config_explosion
      never_cache="1" 
      camera_shake="1.5" 
      explosion_radius="6"
      explosion_sprite="" 
      explosion_sprite_lifetime="0.3" 
      create_cell_probability="0" 
      hole_destroy_liquid="0" 
      hole_enabled="1" 
      damage="0"
      ray_energy="100000"
	  max_durability_to_destroy="10"
      hole_image="data/temp/explosion_hole.png" 
      particle_effect="0" 
      damage_mortals="1" 
      physics_explosion_power.max="0.1"
      physics_throw_enabled="1" 
      shake_vegetation="1" 
      sparks_count_max="2"
      sparks_count_min="1" 
      sparks_enabled="0"
      material_sparks_real="1"
      material_sparks_enabled="1"
      material_sparks_count_max="7"
      material_sparks_count_min="0" 
      gore_particle_count="5"
      light_fade_time="0.025"
      stains_enabled="1"
      stains_radius="2"
      is_digger="1"
      audio_enabled="0" >
    </config_explosion>
    <damage_by_type drill="0.01" >
    </damage_by_type>
  </ProjectileComponent>
```

## Sprite Particle Emitter Component

This component defines visual particles emitted by the projectile.

*   **`sprite_file`**: The XML file defining the particle's appearance (e.g., `smoke_blue.xml`).
*   **`delay`**: Delay before particle emission starts.
*   **`lifetime`**: Duration of individual particles.
*   **`emissive`**: If particles emit light.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: Initial color of the particles.
*   **`velocity.x`, `velocity.y`**: Initial velocity of the particles.
*   **`gravity.x`, `gravity.y`**: Gravity affecting the particles.
*   **`scale.x`, `scale.y`**: Initial scale of the particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Frame interval for emitting particles.
*   **`count_min`, `count_max`**: Number of particles emitted per interval.
*   **`randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`**: Random offset for particle spawn position.

```xml
  <SpriteParticleEmitterComponent
    sprite_file="data/particles/smoke_blue.xml" 
    delay="0"
    lifetime="0"
	  emissive="0"
	  sprite_random_rotation="1"
    color.r="1" color.g="1" color.b="1" color.a="1"
    color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="0"
    velocity.x="0" velocity.y="0"
    gravity.x="0" gravity.y="0"
    velocity_slowdown="0"
    rotation="0"
    angular_velocity="0"
    use_velocity_as_rotation="0"
    scale.x="1" scale.y="1"
    scale_velocity.x="0" scale_velocity.y="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    count_min="1" count_max="1"
    randomize_rotation.min="0"
    randomize_rotation.max="0"
	  randomize_angular_velocity.min="0"
    randomize_angular_velocity.max="0"
    randomize_position.min_x="-1"
    randomize_position.max_x="1"
    randomize_position.min_y="-1"
    randomize_position.max_y="1"
	randomize_velocity.min_y="0"
	randomize_velocity.max_y="0"
	randomize_velocity.min_x="0"
	randomize_velocity.max_x="0"
	render_back="1"
    >
  </SpriteParticleEmitterComponent>
```

## Particle Emitter Component

This component defines the emission of actual game particles (e.g., smoke, sparks).

*   **`emitted_material_name`**: The material name of the particles to emit (e.g., "smoke").
*   **`count_min`, `count_max`**: Number of particles emitted per emission event.
*   **`offset.x`, `offset.y`**: Offset from the projectile's position for particle emission.
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: Velocity range for emitted particles.
*   **`lifetime_min`, `lifetime_max`**: Lifetime range for emitted particles.
*   **`create_real_particles`**: If actual game particles are created.
*   **`emit_cosmetic_particles`**: If cosmetic-only particles are created.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Frame interval for particle emission.
*   **`is_emitting`**: Controls if the emitter is active.

```xml
  <ParticleEmitterComponent 
    emitted_material_name="smoke"
    count_min="7"
    count_max="15"
    offset.x="0"
    offset.y="1"
    x_pos_offset_min="0"
    y_pos_offset_min="0"
    x_pos_offset_max="0"
    y_pos_offset_max="0"
    x_vel_min="-10"
    x_vel_max="10"
    y_vel_min="-10"
    y_vel_max="10"
    count_min="5"
    count_max="5"
    lifetime_min="0.1"
    lifetime_max="0.3"
    create_real_particles="1"
    emit_cosmetic_particles="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
    is_emitting="1" >
  </ParticleEmitterComponent>
```

## Variable Storage Component

This component stores variables associated with the entity.

*   **`name`**: The name of the variable.
*   **`value_string`**: The string value of the variable. In this case, it stores the path to the projectile's own XML file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/digger.xml"
		>
	</VariableStorageComponent>
</Entity>
```