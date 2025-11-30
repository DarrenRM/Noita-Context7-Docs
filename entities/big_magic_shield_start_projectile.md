---
title: Big Magic Shield Start Projectile
category: entities
---

---

# Big Magic Shield Start Projectile

This entity defines the initial projectile for the "Big Magic Shield" spell in Noita. It's a special projectile designed to initiate the shield effect rather than deal direct damage.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance acts on the projectile.

### Projectile Component (`<ProjectileComponent>`)

This component governs the projectile's behavior and properties.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Defines a very slight upward trajectory, suggesting it's meant to be cast with minimal arc.
*   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial speed, implying it's spawned at the caster's location and its movement is dictated by other components (likely the Lua script).
*   **`die_on_low_velocity="0"`**: The projectile will not disappear if its velocity drops.
*   **`on_death_explode="0"`**: The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No graphical effects are left behind when it dies.
*   **`on_lifetime_out_explode="0"`**: The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion were to occur (which it doesn't by default), it wouldn't harm the caster.
*   **`penetrate_entities="1"`**: The projectile can pass through other entities.
*   **`damage="0.0"`**: This projectile deals no damage itself.
*   **`on_collision_die="0"`**: The projectile does not die upon colliding with an entity.
*   **`lifetime="5"`**: The projectile exists for 5 seconds before despawning.

### Lua Component (`<LuaComponent>`)

*   **`script_source_file="data/scripts/projectiles/big_magic_shield_start.lua"`**: This is the core of the projectile's functionality. The associated Lua script handles the creation and behavior of the actual magic shield.
*   **`execute_on_added="1"`**: The Lua script is executed immediately when the projectile is added to the game.

### Audio Component (`<AudioComponent>`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound effects.
*   **`event_root="player_projectiles/magic_shield"`**: Defines the specific sound event to play, indicating a "magic shield" sound for player projectiles.

### Variable Storage Component (`<VariableStorageComponent>`)

*   **`name="projectile_file"`**: A variable named `projectile_file`.
*   **`value_string="data/entities/projectiles/deck/big_magic_shield_start.xml"`**: Stores the path to this entity's XML file, likely for reference within the game's logic.