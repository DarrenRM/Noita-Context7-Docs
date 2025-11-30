---
title: Bounce Lightning Projectile Configuration
category: scripts
---

---

# Bounce Lightning Projectile Configuration

This script modifies the `ProjectileComponent` of the entity that fired the bounce lightning projectile. Its primary purpose is to define the visual effect that plays when the projectile bounces.

## Key Attributes Modified

### ProjectileComponent

This component is targeted for modification.

*   **`bounce_fx_file`**: Specifies the `.xml` file to be loaded and played as a visual effect when the projectile bounces.

    *   **Value**: `"data/entities/projectiles/deck/bounce_lightning_launcher.xml"`

## Script Logic

1.  **Get Entity ID**: Retrieves the unique identifier for the current entity.
2.  **Get Parent Entity**: Determines the entity that spawned this projectile. This is crucial for applying modifications to the original projectile's properties.
3.  **Identify Target Entity**: If a parent entity exists, it's considered the target. Otherwise, the current projectile entity itself is the target.
4.  **Retrieve Projectile Components**: Attempts to get the `ProjectileComponent` from the target entity. If none is found, the script exits.
5.  **Edit Projectile Component**: If `ProjectileComponent` exists, the script uses `edit_component` to modify it.
    *   The `bounce_fx_file` attribute is set to `"data/entities/projectiles/deck/bounce_lightning_launcher.xml"`, ensuring the correct visual effect plays upon bouncing.