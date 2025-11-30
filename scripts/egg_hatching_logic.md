---
title: Egg Hatching Logic
category: scripts
---

# Egg Hatching Logic

This script defines the behavior for an egg entity that hatches into other entities. It allows for customization of which entities can be spawned and how many.

## Core Functionality

The primary purpose of this script is to:
1.  Determine which entity to spawn based on a predefined list and a random selection.
2.  Spawn the selected entity (or multiple entities) at the egg's location.
3.  Apply specific modifications to the spawned entities, such as increased health and charming.

## Key Components and Attributes

### Entity Lists

The `entity_lists` table defines various categories of entities that can be spawned. Each category is a list of potential entities, where each entry can be a string (entity name) or a table containing the entity name and a count.

```lua
local entity_lists =
{
	-- monsters = { {"zombie"}, {"zombie", 2}, {"bigzombie"}, {"skullrat"} }, -- Example commented out
	monsters = { {"zombie"}, {"zombie", 2} },
	-- slimes = { {"slimeshooter_nontoxic"}, {"slimeshooter_nontoxic", 2}, {"acidshooter"}, {"lasershooter"} }, -- Example commented out
	slimes = { {"slimeshooter_nontoxic"}, {"slimeshooter_nontoxic", 2} },
	fire = { {"firebug", 3}, {"bigfirebug"} },
	red = { {"bat", 3}, {"tentacler_small"}, {"tentacler"} },
	chilly = { {"tentacler_small"}, {"tentacler"} },
	purple = { {"longleg", 3}, {"longleg", 4}, {"longleg", 5} },
	worms = { {"worm_tiny"}, {"worm"}, {"worm_big"} },
}
```

### Spawning Logic

-   **`entity_list_name`**: This variable, often set by a `VariableStorageComponent`, determines which list from `entity_lists` to use. If not found, it defaults to "monsters".
-   **Random Selection**: The script uses a seeded random number generator based on the egg's position to pick an entry from the selected `entity_list`.
-   **`entity_to_spawn`**: The name of the entity to be spawned.
-   **`entity_count`**: The number of entities to spawn, defaulting to 1.

### Modifications to Spawned Entities

When entities are spawned, several modifications are applied:

-   **Charming**: Spawned entities (except worms) are charmed, meaning they will be friendly to the player.
    -   `GetGameEffectLoadTo( eid, "CHARM", true )`
    -   `ComponentSetValue( charm_component, "frames", -1 )` (for permanent charm)
-   **Health Increase**: The maximum health and current health of spawned entities are increased by a factor of 4.0.
    -   Iterates through `DamageModelComponent` components.
    -   `max_hp = max_hp * 4.0`
-   **Herd ID**: If the player has a `herd_id`, the spawned entities will inherit it, making them part of the player's herd.
    -   `edit_component( eid, "GenomeDataComponent", function(comp,vars) ... )`
-   **Prevent Gold Drop**: The `script_death` component is modified to prevent spawned entities from dropping money upon death.
    -   `ComponentSetValue( lua_comp, "script_death", "" )`

### Sound Effect

-   A hatching sound effect is played upon spawning.
    -   `GamePlaySound( "data/audio/Desktop/projectiles.bank", "player_projectiles/egg/hatch", x, y )`

## Usage Example

To configure an egg to spawn a specific type of entity, you would typically use a `VariableStorageComponent` on the egg entity itself.

```lua
-- Example VariableStorageComponent configuration (in an entity XML file)
<VariableStorageComponent
    name="entity_list"
    value_string="fire" />
```

This would cause the egg to spawn entities from the `fire` list defined in the `entity_lists` table.