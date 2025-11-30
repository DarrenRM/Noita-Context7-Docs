---
title: Gold Explosion Perk
category: entities
---

# Gold Explosion Perk

This entity defines the "Gold Explosion" perk in Noita. When acquired, it causes enemies to explode into gold upon death.

## Key Components

### `ProjectileComponent`

This component governs the behavior of the projectile that is spawned when an enemy dies.

*   **`lifetime`**: `-1` (Indicates the projectile does not despawn on its own).
*   **`penetrate_world`**: `1` (Can pass through world geometry).
*   **`penetrate_entities`**: `1` (Can pass through other entities).
*   **`collide_with_world`**: `0` (Does not collide with the world).
*   **`collide_with_entities`**: `0` (Does not collide with entities).
*   **`speed_min`**, **`speed_max`**: `0` (No initial movement speed).
*   **`do_moveto_update`**: `0` (Does not use movement updates).
*   **`on_death_gfx_leave_sprite`**: `0` (Graphics do not remain after death).
*   **`on_death_explode`**: `1` (Triggers an explosion upon death).
*   **`explosion_dont_damage_shooter`**: `1` (The explosion does not damage the entity that triggered it).
*   **`friendly_fire`**: `0` (Does not damage friendly entities).
*   **`on_collision_die`**: `0` (Does not die on collision).
*   **`on_collision_spawn_entity`**: `0` (Does not spawn entities on collision).
*   **`damage_every_x_frames`**: `999` (Damage is not applied periodically).
*   **`damage`**: `0` (Base damage of the projectile itself is 0).

### `config_explosion`

This nested configuration defines the properties of the explosion that occurs when the projectile dies.

*   **`never_cache`**: `1` (Ensures this explosion effect is not cached, allowing for unique instances).
*   **`camera_shake`**: `0` (No camera shake effect).
*   **`explosion_radius`**: `5` (The radius of the explosion).
*   **`explosion_sprite`**: `data/particles/explosion_040_poof.xml` (The visual effect for the explosion).
*   **`explosion_sprite_lifetime`**: `0` (The sprite's lifetime is not explicitly set, likely tied to the explosion duration).
*   **`create_cell_probability`**: `0` (No cell creation probability).
*   **`ray_energy`**: `200000` (High energy for potential physics interactions).
*   **`hole_destroy_liquid`**: `0` (Does not destroy liquids).
*   **`damage`**: `4` (The damage dealt by the explosion).
*   **`hole_enabled`**: `1` (Enables the creation of holes in terrain).
*   **`hole_image`**: `data/temp/explosion_hole.png` (The image used for the terrain hole).
*   **`particle_effect`**: `1` (Enables particle effects for the explosion).
*   **`damage_mortals`**: `1` (Deals damage to mortal entities).
*   **`physics_explosion_power.min`**: `0.1` (Minimum physics force applied by the explosion).
*   **`physics_explosion_power.max`**: `1.6` (Maximum physics force applied by the explosion).
*   **`physics_throw_enabled`**: `1` (Enables physics-based throwing of objects).
*   **`shake_vegetation`**: `1` (Causes vegetation to shake).
*   **`sparks_enabled`**: `1` (Enables spark effects).
*   **`sparks_count_max`**: `30` (Maximum number of sparks).
*   **`sparks_count_min`**: `5` (Minimum number of sparks).
*   **`light_fade_time`**: `0.8` (Time for the light effect to fade).
*   **`stains_enabled`**: `1` (Enables stain effects on surfaces).
*   **`stains_image`**: `data/temp/explosion_stain.png` (The image used for stains).