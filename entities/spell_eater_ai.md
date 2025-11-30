---
title: Spell Eater AI
category: entities
---

# Spell Eater AI

This script controls the behavior of the Spell Eater entity, a component of the boss robot. It primarily focuses on detecting and consuming incoming projectiles.

## Core Functionality

The Spell Eater's behavior is determined by a `VariableStorageComponent` named "spell_eater".

*   **State 0:** The Spell Eater is inactive. Its associated components are disabled.
*   **State > 0:** The Spell Eater is active. Its associated components are enabled.

## Projectile Consumption Logic

When active, the Spell Eater attempts to consume projectiles within a certain radius and angle.

### Key Attributes & Behaviors

*   **`distance_full`**: Defines the radius (in pixels) around the Spell Eater within which it can detect projectiles.
*   **Targeting**: The Spell Eater attempts to face the nearest player.
*   **Projectile Detection**: It scans for entities tagged as "projectile" within its `distance_full`.
*   **Angle Check**: Projectiles are only considered for consumption if they are within a specific angular range (approximately 82 degrees) relative to the Spell Eater's facing direction.
*   **Consumption**:
    *   If a projectile is within range and angle, and was *not* shot by the boss robot itself, it is destroyed.
    *   The `on_death_explode` and `on_lifetime_out_explode` properties of the consumed projectile are set to `false` to prevent unintended explosions.

### Important Components & Variables

*   **`VariableStorageComponent`**: Used to store the `state` of the Spell Eater (0 for inactive, >0 for active).
*   **`EntityGetInRadiusWithTag`**: Used to find nearby projectiles.
*   **`EntityGetTransform`**: Used to get the position and rotation of entities.
*   **`EntitySetTransform`**: Used to update the Spell Eater's rotation.
*   **`EntityKill`**: Used to destroy projectiles.
*   **`ProjectileComponent`**: Accessed to determine who shot the projectile and modify its explosion behavior.

## AI State Management

The script dynamically enables or disables the Spell Eater's visual and functional components based on its `state` variable.

```lua
-- Example of state check and component enabling/disabling
if ( state == 0 ) then
	EntitySetComponentsWithTagEnabled( entity_id, "boss_robot_spell_eater", false )
else
	EntitySetComponentsWithTagEnabled( entity_id, "boss_robot_spell_eater", true )
	-- ... projectile consumption logic ...
end
```