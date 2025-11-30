---
title: Boss Spirit Entity Configuration
category: entities
---

# Boss Spirit Entity Configuration

This document details the configuration for the Boss Spirit entity in Noita, focusing on its dynamic scaling and associated wisps.

## Core Attributes

The Boss Spirit's behavior and stats are primarily influenced by the global variable `HELPLESS_KILLS`, which tracks the number of defeated animals.

### Dynamic Health Scaling

The maximum and current HP of the Boss Spirit are dynamically adjusted based on the `HELPLESS_KILLS` global.

*   **`anger`**: A numerical value derived from `HELPLESS_KILLS`. Defaults to 1 if the global is not found or invalid.
*   **`boss_hp`**: Calculated as `20.0 + anger * 4`, capped at a maximum of 2000. This value sets both `max_hp` and `hp` for the `DamageModelComponent`.

```lua
local anger = tonumber( GlobalsGetValue( "HELPLESS_KILLS", "1" ) ) or 1
local boss_hp = math.min(20.0 + anger * 4, 2000)
local comp = EntityGetFirstComponent( entity_id, "DamageModelComponent" )

if( comp ~= nil ) then
	ComponentSetValue( comp, "max_hp", tostring(boss_hp) )
	ComponentSetValue( comp, "hp", tostring(boss_hp) )
end
```

### Wisp Spawning

The Boss Spirit can spawn "wisps" based on the `HELPLESS_KILLS` count.

*   **`wispnum`**: The number of wisps to spawn, calculated as `math.min( math.ceil( anger / 10 ), 20 )`. This means wisps start appearing when `anger` reaches 10 and are capped at 20.
*   **Wisp Placement**: Each spawned wisp is placed with a slight vertical offset from the Boss Spirit's position, determined by a procedural random value.
*   **Wisp Entity**: Wisps are loaded from `data/entities/animals/boss_spirit/wisp.xml`.

```lua
local wispnum = math.min( math.ceil( anger / 10 ), 20 )
if ( wispnum > 0 ) then
	for i=1,wispnum do
		local r = ProceduralRandomf(entity_id + i, 0, -1, 1)
		local offset = r * 24
		local wid = EntityLoad( "data/entities/animals/boss_spirit/wisp.xml", x, y + offset )
		EntityAddChild( entity_id, wid )
	end
end
```