---
title: Boss Alchemist Wand Projectile Logic
category: entities
---

# Boss Alchemist Wand Projectile Logic

This script defines the projectile behavior for the Boss Alchemist's wand. It randomly selects one of four projectile types (darkness, electricity, light, fire) and assigns it to the wand's `VariableStorageComponent`.

## Key Components

### `styles` Table

This table defines the available projectile types and their corresponding projectile XML files.

| Name       | Projectile XML Path                                    |
|------------|--------------------------------------------------------|
| `darkness` | `data/entities/projectiles/enlightened_laser_dark_wand.xml` |
| `electricity` | `data/entities/projectiles/enlightened_laser_elec_wand.xml` |
| `light`    | `data/entities/projectiles/enlightened_laser_light_wand.xml` |
| `fire`     | `data/entities/projectiles/enlightened_laser_fire_wand.xml` |

### Random Selection

The script uses the entity's position and ID to generate a random seed, ensuring a different projectile type is chosen each time the boss spawns.

```lua
SetRandomSeed( x * entity_id, y * entity_id )
local rnd = Random( 1, #styles )
local style = styles[rnd]
```

### Variable Storage Component Update

The selected projectile path is then stored in the `VariableStorageComponent` of the Boss Alchemist entity, specifically under the `type` variable.

```lua
local s = EntityGetComponent( entity_id, "VariableStorageComponent" )
if ( s ~= nil ) then
	for i,v in ipairs( s ) do
		local name = ComponentGetValue2( v, "name" )
		
		if ( name == "type" ) then
			ComponentSetValue2( v, "value_string", style.proj )
		end
	end
end
```