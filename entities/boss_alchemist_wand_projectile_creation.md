---
title: Boss Alchemist Wand Projectile Creation
category: entities
---

---

# Boss Alchemist Wand Projectile Creation

This script defines the behavior for the Boss Alchemist's wand, specifically how it creates and fires projectiles. It targets the player and fires a projectile based on a stored type.

## Key Components and Logic

### Entity Initialization

-   `entity_id`: Retrieves the unique identifier for the current entity.
-   `x, y`: Gets the current position of the entity.
-   `radius`: Defines the detection radius for targeting the player (260 units).

### Projectile Type Determination

-   The script searches for a `VariableStorageComponent` attached to the entity.
-   Within this component, it looks for a variable named `"type"`.
-   The `value_string` of this variable is assigned to the `proj` variable, determining which projectile will be fired.

### Player Targeting and Projectile Firing

-   `EntityGetInRadiusWithTag(x, y, radius, "player_unit")`: Detects entities with the tag `"player_unit"` within the specified radius.
-   The script proceeds only if a projectile type (`string.len(proj) > 0`) has been determined and at least one player target is found (`#targets > 0`).
-   For each player target:
    -   The player's position (`px, py`) is retrieved.
    -   The velocity (`vel_x`, `vel_y`) of the projectile is calculated to aim directly at the player. The speed is set to 2.0.
    -   `shoot_projectile_from_projectile(entity_id, proj, x, y, vel_x, vel_y)`: This function is called to fire the determined projectile (`proj`) from the wand's position (`x, y`) with the calculated velocity.
    -   `EntityAddTag(eid, "boss_alchemist")`: The newly created projectile is tagged with `"boss_alchemist"`.

## Key Attributes

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `radius`       | The detection range for the player.                                      |
| `proj`         | Stores the string name of the projectile to be fired.                    |
| `player_unit`  | The tag used to identify the player entity.                              |
| `vel_x`, `vel_y` | Calculated velocity components for projectile aiming.                    |
| `boss_alchemist` | A tag applied to the fired projectiles, likely for identification. |