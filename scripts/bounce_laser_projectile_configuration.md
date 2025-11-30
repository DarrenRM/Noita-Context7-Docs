---
title: Bounce Laser Projectile Configuration
category: scripts
---

---

# Bounce Laser Projectile Configuration

This script modifies the `ProjectileComponent` of a parent entity to configure the bounce laser projectile. It primarily sets the visual effect file for when the projectile bounces.

## Key Attributes Modified

### ProjectileComponent

This component is targeted for modification.

*   **`bounce_fx_file`**: Specifies the `.xml` file to be used for the visual effects when the projectile bounces.
    *   **Value**: `"data/entities/projectiles/deck/bounce_laser_launcher.xml"`

## Logic Overview

1.  **Get Entity ID and Transform**: Retrieves the current entity's ID and its position.
2.  **Identify Parent Entity**: Determines the parent entity of the projectile. This is crucial as the configuration is applied to the entity that *fired* the projectile, not the projectile itself.
3.  **Target Entity Selection**: If a parent entity exists, it's selected as the target for modification. Otherwise, the projectile entity itself is used (though this is less common for this specific script's intent).
4.  **Component Editing**:
    *   It attempts to retrieve the `ProjectileComponent` from the `target_id`.
    *   If the component exists and has elements, it uses `edit_component` to modify the `bounce_fx_file` attribute.