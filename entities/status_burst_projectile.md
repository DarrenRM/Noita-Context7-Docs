---
title: Status Burst Projectile
category: entities
---

# Status Burst Projectile

This entity defines a projectile used by the boss wizard, primarily for applying status effects rather than direct damage.

## Key Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.8"`: A relatively low mass.

### Projectile Behavior (`ProjectileComponent`)

This component governs the projectile's movement, interaction, and effects.

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile.
*   **`speed_min="100"`, `speed_max="120"`**: Defines the projectile's speed range.
*   **`die_on_low_velocity="0"`**: The projectile does not die if its velocity becomes low.
*   **`on_death_explode="0"`**: No explosion upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No sprite left behind upon death.
*   **`on_lifetime_out_explode="0"`**: No explosion when lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion were to occur, it wouldn't damage the shooter.
*   **`damage="0"`**: The projectile itself deals no damage.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`lifetime="100"`**: The projectile exists for 100 frames.
*   **`knockback_force="2.0"`**: Applies a knockback force of 2.0 upon collision.
*   **`penetrate_entities="1"`**: Can pass through entities.
*   **`penetrate_world="1"`**: Can pass through the world geometry.

#### `config_explosion`

*   `damage="0"`: No damage from any potential explosion.
*   `explosion_radius="1"`: A very small explosion radius.

### Scripted Behavior (`LuaComponent`)

This component enables custom scripting for the projectile.

*   **`script_source_file="data/entities/animals/boss_wizard/statusburst.lua"`**: Links to the Lua script that defines the projectile's specific behavior, likely related to applying status effects.
*   **`execute_every_n_frame="2"`**: The associated Lua script runs every 2 frames.

### Lifetime (`LifetimeComponent`)

*   **`lifetime="20"`**: The projectile's visual lifetime is 20 frames. This might be distinct from the `ProjectileComponent` lifetime, potentially affecting visual disappearance before the projectile itself ceases to exist.