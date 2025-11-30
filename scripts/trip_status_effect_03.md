---
title: Trip Status Effect (03)
category: scripts
---

---

# Trip Status Effect (03)

This script defines a status effect in Noita that triggers a visual and environmental change. It's primarily used for the "Trip" status effect, likely associated with certain spells or environmental interactions.

## Key Functionality

*   **Visual Effect:** Spawns "treble eye" particles around the affected entity.
*   **Environmental Shift:** Triggers a `fungal_shift` event, altering materials in the environment.

## Core Components

### Particle Spawning

The script conditionally spawns "treble eye" particles.

*   **Condition:** `rand(0,1) > 0.5` - A 50% chance to spawn particles.
*   **Particle Type:** `data/entities/particles/treble_eye.xml`
*   **Spawn Logic:**
    *   Particles are spawned relative to the entity's position (`pos_x`, `pos_y`).
    *   A random offset is applied to the initial spawn point.
    *   Three particles are spawned with varying offsets to create a visual spread.

```lua
-- Example of particle spawning logic
if ( rand(0,1) > 0.5 ) then
	function spawn( x,y )
		EntityLoad( "data/entities/particles/treble_eye.xml", x,y )
	end

	local x,y = pos_x + rand(-100,100), pos_y + rand(-80,80)
	local rad = rand(0,30)

	spawn(x,y)
	spawn( x + 40 + rad, y + 30 + rad )
	spawn( x - 40 - rad, y + 30 + rad )
end
```

### Material Shifting

The script utilizes the `fungal_shift` function to alter the game's materials.

*   **Function:** `fungal_shift( entity_id, pos_x, pos_y, false )`
    *   `entity_id`: The ID of the entity experiencing the effect.
    *   `pos_x`, `pos_y`: The coordinates where the shift originates.
    *   `false`: A boolean parameter, its specific effect within `fungal_shift` is not detailed here but likely controls certain aspects of the shift.

```lua
-- Example of material shifting
fungal_shift( entity_id, pos_x, pos_y, false )
```

## Dependencies

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/magic/fungal_shift.lua`