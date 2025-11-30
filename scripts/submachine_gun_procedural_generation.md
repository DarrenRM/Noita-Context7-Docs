---
title: Submachine Gun Procedural Generation
category: scripts
---

---

# Submachine Gun Procedural Generation

This script defines a system for procedurally generating submachine guns in Noita. It uses a predefined list of gun configurations, each with a `chance` to be selected, and then applies modifications to create unique variations.

## Key Gun Configurations

The `guns` table contains the base configurations for submachine guns. Each entry represents a potential submachine gun type with specific properties.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `chance`              | The probability of this gun configuration being selected.                   |
| `capacity`            | The maximum number of projectiles the gun can hold before reloading.        |
| `actions_per_round`   | The number of projectiles fired each time the trigger is pulled.            |
| `reload`              | The time (in frames) it takes for the gun to reload.                        |
| `shuffle`             | Whether the order of projectiles in `actions` should be randomized.         |
| `rare_chance`         | The probability of a rare variant of this gun being generated.              |
| `rare_type`           | A string identifier for the type of rare variant (e.g., "test").            |
| `actions`             | A list of projectile types to be fired by the gun.                          |

### Example Configurations:

```lua
local guns =
{
	{
		chance = 0.1,
		capacity = 10,
		actions_per_round = 1,
		reload = 70,
		shuffle = true,
		rare_chance = 0.1,
		rare_type = "test",
		actions =
		{
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
		},
	},
	{
		chance = 0.2,
		capacity = 8,
		actions_per_round = 1,
		reload = 50,
		shuffle = true,
		actions =
		{
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
			"SPITTER",
		},
	},
	-- ... more configurations can be added here
}
```

## Generation Logic

The `generate_gun()` function is responsible for creating a new submachine gun entity.

1.  **Entity Placement:** It retrieves the entity's current position (`x`, `y`).
2.  **Random Seed:** A random seed is set based on the entity's position to ensure consistent generation for the same location.
3.  **Probability Calculation:** It iterates through the `guns` table, calculating cumulative chances to determine which gun configuration will be selected.
4.  **Gun Selection:** A random number is generated, and based on the cumulative chances, a specific gun configuration is chosen.
5.  **Base Gun Generation:** The `gun_gen()` function (presumably from `gun_utilities.lua`) is called to create the base gun entity with the selected properties.

## Rare Variant Modification

The `rare_gun()` function handles applying modifications to create rare variants of guns.

*   It takes a base gun configuration (`g`) and the entity ID as input.
*   It retrieves base properties like `capacity`, `actions_per_round`, `reload`, `shuffle`, `firerate`, `spread`, and `bullet_speed`.
*   **Specific Rare Type Logic:** If `rare_type` is "test", it modifies `bullet_speed` to `0.9`.
*   It returns the potentially modified gun properties.

```lua
function rare_gun(g,entity_id)
	local capacity = g.capacity
	local actions_per_round = g.actions_per_round
	local reload = g.reload
	local shuffle = g.shuffle
	local firerate = g.firerate
	local spread = g.spread
	local bullet_speed = g.bullet_speed
	local rare_type = g.rare_type

	if (rare_type == "test") then
		bullet_speed = 0.9
	end

	return capacity,actions_per_round,reload,shuffle,firerate,spread,bullet_speed
end
```

## Dependencies

*   `dofile('data/scripts/gun/procedural/gun_utilities.lua')`: This script is required for the `gun_gen()` function, which handles the actual creation of the gun entity in the game world.