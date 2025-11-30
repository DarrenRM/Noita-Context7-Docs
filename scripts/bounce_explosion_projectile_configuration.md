---
title: Bounce Explosion Projectile Configuration
category: scripts
---

---

# Bounce Explosion Projectile Configuration

This script configures a projectile to trigger a "bounce explosion" effect. It identifies the projectile's parent entity and, if found, modifies its `ProjectileComponent` to specify the visual effect file for the bounce.

## Key Components and Logic

### Entity Identification
- `GetUpdatedEntityID()`: Retrieves the unique identifier for the current entity.
- `EntityGetTransform()`: Gets the position (x, y) of the entity.
- `EntityGetParent()`: Determines the parent entity of the current projectile. This is crucial for applying the effect to the entity that fired the projectile.

### Target Entity Determination
- The script prioritizes the `parent_id` as the `target_id`.
- If no parent is found (e.g., the projectile is the root entity), the `entity_id` itself becomes the `target_id`.

### Projectile Component Modification
- `EntityGetComponent( target_id, "ProjectileComponent" )`: Attempts to retrieve the `ProjectileComponent` from the determined target entity.
- If the `ProjectileComponent` is not found, the script exits.
- `edit_component()`: This function is used to modify the properties of the `ProjectileComponent`.

### Bounce FX Configuration
- `vars.bounce_fx_file = "data/entities/projectiles/deck/bounce_explosion.xml"`: This is the core configuration. It sets the `bounce_fx_file` property of the `ProjectileComponent` to point to an XML file that defines the visual effects of the bounce explosion.

## Summary of Functionality

The primary purpose of this script is to dynamically link a bounce explosion visual effect to a projectile. It achieves this by:
1.  Identifying the projectile and its potential parent.
2.  Locating the `ProjectileComponent` on the relevant entity.
3.  Assigning a specific XML file (`data/entities/projectiles/deck/bounce_explosion.xml`) to the `bounce_fx_file` property of the `ProjectileComponent`.

This allows for a consistent and configurable bounce explosion effect across different projectiles that utilize this script.