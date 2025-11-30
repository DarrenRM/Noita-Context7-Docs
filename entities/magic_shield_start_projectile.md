---
title: Magic Shield Start Projectile
category: entities
---

---

# Magic Shield Start Projectile

This entity defines the initial projectile for the "Magic Shield" spell in Noita. It's a special projectile designed to create a shield effect rather than deal direct damage.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance acts on the projectile.

### Projectile Component (`<ProjectileComponent>`)

This component governs the projectile's behavior and properties.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile. These values suggest a very straight trajectory with minimal lob.
*   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial speed. It's likely propelled by other means or its effect is triggered immediately.
*   **`die_on_low_velocity="0"`**: The projectile will not disappear if its velocity drops.
*   **`on_death_explode="0"`**: The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No graphical effects are left behind when the projectile dies.
*   **`on_lifetime_out_explode="0"`**: The projectile does not explode when its lifetime ends.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion were to occur (which it doesn't by default), it wouldn't harm the shooter.
*   **`penetrate_entities="1"`**: The projectile can pass through other entities.
*   **`damage="0.0"`**: This projectile deals no direct damage.
*   **`on_collision_die="0"`**: The projectile does not die upon colliding with something.
*   **`lifetime="5"`**: The projectile exists for 5 seconds before expiring.

### Lua Component (`<LuaComponent>`)

*   **`script_source_file="data/scripts/projectiles/magic_shield_start.lua"`**: This specifies the Lua script that controls the unique behavior of this projectile, likely responsible for spawning the shield effect.
*   **`execute_on_added="1"`**: The Lua script is executed as soon as the projectile is added to the game.

### Audio Component (`<AudioComponent>`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: Points to the audio bank containing projectile sounds.
*   **`event_root="player_projectiles/magic_shield"`**: Specifies the audio event to play, likely a sound associated with the magic shield being cast.

### Variable Storage Component (`<VariableStorageComponent>`)

*   **`name="projectile_file"`**: A variable named "projectile\_file".
*   **`value_string="data/entities/projectiles/deck/magic_shield_start.xml"`**: Stores the path to this entity's XML file, useful for referencing itself within the game.