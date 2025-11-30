---
title: Revenge Explosion Perk Projectile
category: entities
---

# Revenge Explosion Perk Projectile

This entity defines the projectile used by the "Revenge Explosion" perk in Noita. When the player is hit, this projectile is spawned and detonates after a short duration or upon collision, creating an explosion.

## Key Components and Attributes

### Base Projectile (`Base`)

*   **`VelocityComponent`**:
    *   `gravity_y`: Controls the downward acceleration of the projectile. Set to `100` for moderate gravity.

### Projectile Component (`ProjectileComponent`)

This is the core component defining the projectile's behavior.

*   **`_enabled`**: `1` - Enables the component.
*   **`lob_min`, `lob_max`**: `0.8`, `1.0` - Defines the minimum and maximum lobbing behavior (arc of the projectile).
*   **`speed_min`, `speed_max`**: `160`, `170` - Sets the projectile's initial speed range.
*   **`on_death_explode`**: `1` - The projectile will explode when it dies.
*   **`on_death_gfx_leave_sprite`**: `0` - Does not leave a sprite graphic upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile will explode when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - Prevents the explosion from damaging the player who spawned it.
*   **`die_on_low_velocity`**: `1` - The projectile will die if its velocity drops too low.
*   **`damage`**: `0` - The projectile itself deals no direct damage. Damage is handled by the explosion.
*   **`on_collision_die`**: `1` - The projectile dies upon colliding with something.
*   **`lifetime`**: `1` - The projectile exists for 1 second before expiring.

#### Explosion Configuration (`config_explosion`)

This nested component defines the properties of the explosion triggered by the projectile.

*   **`never_cache`**: `0` - Allows caching of the explosion for performance.
*   **`camera_shake`**: `13` - The intensity of camera shake caused by the explosion.
*   **`damage`**: `6` - The damage dealt by the explosion.
*   **`explosion_radius`**: `72` - The radius of the explosion's effect.
*   **`explosion_sprite`**: `data/particles/explosion_040_poof.xml` - The visual sprite used for the explosion effect.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_small.xml` - The entity to load for the main explosion particle effect.
*   **`explosion_sprite_lifetime`**: `0` - The explosion sprite does not have a separate lifetime.
*   **`explosion_sprite_random_rotation`**: `0` - The explosion sprite does not have random rotation.
*   **`create_cell_probability`**: `0` - No chance of creating material cells.
*   **`create_cell_material`**: `spark` - Material of cells created (though probability is 0).
*   **`hole_destroy_liquid`**: `0` - Does not destroy liquids.
*   **`hole_enabled`**: `1` - Creates a hole in the terrain.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the terrain hole.
*   **`particle_effect`**: `1` - Enables particle effects for the explosion.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `1.0`, `1.7` - The minimum and maximum force applied to physics objects by the explosion.
*   **`physics_throw_enabled`**: `1` - Physics objects can be thrown by the explosion.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake.
*   **`sparks_count_min`, `sparks_count_max`**: `70`, `80` - The range for the number of sparks generated.
*   **`sparks_enabled`**: `1` - Enables spark generation.
*   **`stains_enabled`**: `1` - Enables stain generation on surfaces.
*   **`stains_image`**: `data/temp/explosion_stain.png` - The image used for explosion stains.
*   **`audio_event_name`**: `explosions/revenge_perk` - The sound event triggered by the explosion.
*   **`ray_energy`**: `300000` - The energy value for raycasting effects, potentially related to damage or interaction.

### Variable Storage (`VariableStorageComponent`)

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/misc/perks/revenge_explosion.xml` - Stores the path to this entity's XML file, likely for internal referencing.