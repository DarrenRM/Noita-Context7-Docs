---
title: Fungitrap Projectile (fungitrap_02_projectile)
category: entities
---

# Fungitrap Projectile (fungitrap_02_projectile)

This entity defines the projectile fired by the `fungitrap_02` building. It's a simple projectile designed to spawn another entity upon collision.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

*   **`<VelocityComponent mass="1.4">`**: Defines the projectile's mass.

### Projectile Component (`<ProjectileComponent>`)

This is the core component defining the projectile's behavior.

*   **`speed_min="200"` / `speed_max="200"`**: Sets a fixed projectile speed.
*   **`die_on_low_velocity="0"`**: The projectile will not die if its velocity drops too low.
*   **`on_death_explode="0"`**: The projectile does not explode when it dies.
*   **`on_death_gfx_leave_sprite="0"`**: No graphical effects are left behind when the projectile dies.
*   **`on_lifetime_out_explode="0"`**: The projectile does not explode when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
*   **`penetrate_entities="1"`**: The projectile can pass through entities.
*   **`collide_with_entities="0"`**: The projectile does not collide with entities (this seems contradictory to `penetrate_entities="1"`, likely meaning it doesn't trigger collision effects *on* entities it passes through, but still dies on collision).
*   **`damage="0"`**: The projectile itself deals no damage.
*   **`lifetime="40"`**: The projectile exists for 40 frames before expiring.
*   **`on_collision_spawn_entity="1"`**: Spawns another entity upon collision.
*   **`spawn_entity="data/entities/buildings/fungitrap_02_spawner.xml"`**: Specifies the entity to spawn upon collision.

### Explosion Configuration (`<config_explosion>`)

This section is largely disabled for this projectile, as it doesn't cause an explosion.

*   **`damage="0"`**: No damage from explosion.
*   **`explosion_radius="0"`**: No explosion radius.
*   **`physics_explosion_power.min="0"` / `physics_explosion_power.max="0"`**: No physics-based explosion force.
*   **`sparks_enabled="0"`**: No sparks are generated.
*   **`stains_enabled="0"`**: No stains are left behind.