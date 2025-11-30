---
title: Fungitrap Projectile Spawner
category: scripts
---

---

# Fungitrap Projectile Spawner

This script controls the behavior of the `fungitrap_01` building, specifically its chance to spawn a projectile.

## Core Functionality

The primary purpose of this script is to randomly trigger the spawning of a projectile associated with the fungitrap.

### Key Attributes

*   **`entity_id`**: Unique identifier for the fungitrap entity.
*   **`x`, `y`**: Coordinates of the fungitrap entity.
*   **`rnd`**: A random number generated between 1 and 7. This determines the probability of projectile spawning.
*   **`angle`**: A random angle (in radians) between 0 and 180 degrees, used for projectile trajectory.
*   **`speed`**: The base speed of the spawned projectile (set to 200).
*   **`vel_x`, `vel_y`**: Calculated velocity components for the projectile based on `angle` and `speed`.

### Projectile Spawning Logic

The script checks if the randomly generated number `rnd` is equal to 5. If it is, a projectile is spawned. This means there is a 1 in 7 chance (approximately 14.3%) for the fungitrap to fire a projectile on any given frame.

```lua
-- Probability check for projectile spawning
if ( rnd == 5 ) then
	-- Function to shoot the projectile
	shoot_projectile( entity_id, "data/entities/buildings/fungitrap_01_projectile.xml", x, y, vel_x, vel_y )
end
```

### Projectile Definition

The projectile itself is defined by the XML file: `"data/entities/buildings/fungitrap_01_projectile.xml"`. This script only dictates *when* and *how* it is fired.