---
title: gun_actions
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/gun_actions.lua
---

# gun_actions

This file, `gun_actions.lua`, is a core component of Noita's gun and spell system. It defines a collection of "actions" that can be applied to a player's wand. These actions represent various effects, from firing specific projectiles to modifying the wand's behavior. Essentially, this file acts as a library of potential spell components that can be combined to create unique and powerful wands. The game dynamically loads and references these actions to determine what happens when a wand is fired or when certain conditions are met.

## File Structure

The `gun_actions.lua` file is structured as a Lua table named `actions`. Each entry within this table represents a single gun action and is itself a Lua table containing various key-value pairs that define the action's properties and behavior.

The general structure for an action entry is as follows:

```lua
{
    id          = "UNIQUE_ACTION_ID",
    name        = "$localization_key_for_name",
    description = "$localization_key_for_description",
    sprite      = "path/to/sprite.png",
    -- Optional fields like sprite_unidentified, related_projectiles, etc.
    type        = ACTION_TYPE_CONSTANT,
    spawn_level = "level_list", -- Comma-separated string of spawn levels
    spawn_probability = "probability_list", -- Comma-separated string of probabilities
    price       = number,
    mana        = number,
    max_uses    = number, -- Or -1 for infinite uses
    -- Optional fields like custom_xml_file, spawn_requires_flag
    action      = function()
        -- Lua code defining the action's effect
    end,
},
```

**Key Fields Observed:**

*   **`id`**: A unique string identifier for the action.
*   **`name`**: A localization key (prefixed with `$`) used to display the action's name in-game.
*   **`description`**: A localization key (prefixed with `$`) used to display the action's description in-game.
*   **`sprite`**: The file path to the sprite used to represent the action in the UI.
*   **`sprite_unidentified`**: (Optional) The file path to a sprite shown when the action is unidentified.
*   **`related_projectiles`**: (Optional) A Lua table containing file paths to projectile entities associated with this action.
*   **`related_extra_entities`**: (Optional) A Lua table containing file paths to other entities (like effects or modifiers) associated with this action.
*   **`type`**: A constant indicating the category of the action (e.g., `ACTION_TYPE_PROJECTILE`, `ACTION_TYPE_MODIFIER`).
*   **`spawn_level`**: A comma-separated string indicating the game levels where this action can spawn.
*   **`spawn_probability`**: A comma-separated string of probabilities corresponding to the `spawn_level` entries.
*   **`price`**: The in-game cost of the action.
*   **`mana`**: The mana cost to use the action.
*   **`max_uses`**: The maximum number of times the action can be used before it's depleted. A value of `-1` typically indicates infinite uses.
*   **`custom_xml_file`**: (Optional) A file path to an XML file that defines custom behavior or entities for this action.
*   **`spawn_requires_flag`**: (Optional) A string representing a game flag that must be active for this action to spawn.
*   **`action`**: A Lua function that contains the game logic executed when this action is triggered. This function often modifies global variables (like `c` for current wand properties) or calls game functions (like `add_projectile`).

## Key Patterns

Several patterns emerge from the sampled content:

*   **Action Types**: Actions are categorized by their `type`. The most prominent types observed are `ACTION_TYPE_PROJECTILE` (actions that spawn projectiles) and `ACTION_TYPE_MODIFIER` (actions that alter wand properties or add effects).
*   **Projectile Spawning**: Actions of type `ACTION_TYPE_PROJECTILE` typically use the `add_projectile()` or `add_projectile_trigger_hit_world()` functions within their `action` block, specifying the XML path to the projectile entity.
*   **Wand Modification**: Actions of type `ACTION_TYPE_MODIFIER` often directly manipulate properties of the `c` (current wand) table, such as `c.fire_rate_wait`, `c.spread_degrees`, `c.damage_projectile_add`, `c.bounces`, etc. They can also add extra entities or effects using `c.extra_entities` or `c.game_effect_entities`.
*   **Localization Keys**: Names and descriptions consistently use Lua string formatting with a `$` prefix, indicating they are intended to be looked up in localization files for multi-language support.
*   **Spawn Logic**: The `spawn_level` and `spawn_probability` fields provide a mechanism for controlling where and how often a particular action appears in the game's progression.
*   **Comments for Testing/Development**: The presence of commented-out sections, like the `TESTBULLET` example, suggests that this file is actively used during development and testing.
*   **Chained Effects**: Some actions, particularly modifiers, use `draw_actions( 1, true )` within their `action` function. This likely triggers the rendering of visual effects associated with applying the modifier.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `BOMB` Action (Projectile)**

```lua
	{
		id          = "BOMB",
		name 		= "$action_bomb",
		description = "$actiondesc_bomb",
		sprite 		= "data/ui_gfx/gun_actions/bomb.png",
		sprite_unidentified = "data/ui_gfx/gun_actions/bomb_unidentified.png",
		related_projectiles	= {"data/entities/projectiles/bomb.xml"},
		type 		= ACTION_TYPE_PROJECTILE,
		spawn_level                       = "0,1,2,3,4,5,6", -- BOMB
		spawn_probability                 = "1,1,1,1,0.5,0.5,0.1", -- BOMB
		price = 200,
		mana = 25,
		max_uses    = 3,
		custom_xml_file = "data/entities/misc/custom_cards/bomb.xml",
		action 		= function()
			add_projectile("data/entities/projectiles/bomb.xml")
			c.fire_rate_wait = c.fire_rate_wait + 100
		end,
	},
```
This entry defines the "Bomb" action. It's a projectile type that spawns a `bomb.xml` entity. It has a specific sprite, can spawn across many levels with decreasing probability, costs 200 gold and 25 mana, and has a limited use of 3. The `action` function adds the bomb projectile and increases the wand's fire rate wait time.

**2. `DISC_BULLET` Action (Projectile)**

```lua
		type 		= ACTION_TYPE_PROJECTILE,
		spawn_level                       = "0,2,4", -- DISC_BULLET
		spawn_probability                 = "1,1,0.6", -- DISC_BULLET
		price = 120,
		mana = 20,
		--max_uses = 40,
		action 		= function()
			add_projectile("data/entities/projectiles/deck/disc_bullet.xml")
			-- damage = 0.3
			c.fire_rate_wait = c.fire_rate_wait + 10
			c.spread_degrees = c.spread_degrees + 2.0
			shot_effects.recoil_knockback = 20.0
		end,
	},
```
This is another projectile action, "Disc Bullet". It spawns a `disc_bullet.xml` projectile. It's available in earlier levels with higher probability. Its action adds the projectile, increases fire rate wait, increases spread, and applies recoil knockback. The commented-out `damage = 0.3` suggests this might be a base damage value that can be modified by other factors.

**3. `TRUE_ORBIT` Action (Modifier)**

```lua
	{
		id          = "TRUE_ORBIT",
		name 		= "$action_true_orbit",
		description = "$actiondesc_true_orbit",
		sprite 		= "data/ui_gfx/gun_actions/true_orbit.png",
		sprite_unidentified = "data/ui_gfx/gun_actions/sinewave_unidentified.png",
		related_extra_entities = { "data/entities/misc/true_orbit.xml" },
		type 		= ACTION_TYPE_MODIFIER,
		spawn_level                       = "2,3,4", -- HORIZONTAL_ARC
		spawn_probability                 = "0.2,0.3,0.4", -- HORIZONTAL_ARC
		price = 40,
		mana = 2,
		--max_uses = 150,
		action 		= function()
			c.extra_entities = c.extra_entities .. "data/entities/misc/true_orbit.xml,"
			draw_actions( 1, true )
			c.damage_projectile_add = c.damage_projectile_add + 0.1
			c.fire_rate_wait    = c.fire_rate_wait - 20
			c.lifetime_add 		= c.lifetime_add + 80
		end,
	},
```
This entry defines a modifier action, "True Orbit". It doesn't spawn a projectile directly but modifies the wand's behavior. It adds an extra entity (`true_orbit.xml`), increases projectile damage, decreases fire rate wait, and increases projectile lifetime. The `draw_actions( 1, true )` call suggests visual feedback for applying this modifier.

## Reference

This file contains 11126 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/gun_actions.lua).

---