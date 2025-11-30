---
title: _gun_actions_unlimited
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/_gun_actions_unlimited.lua
---

# _gun_actions_unlimited

This file, `_gun_actions_unlimited.lua`, defines a comprehensive collection of "actions" or "cards" that players can acquire and use in the game Noita. These actions are fundamental to the game's core mechanics, particularly how players interact with their wands and modify their projectile behavior. The file essentially acts as a database for all available wand actions, dictating their properties, effects, and how they are triggered. This includes actions that modify projectile behavior, draw more cards, change projectile patterns, or even alter the player's own sprite.

## File Structure

The file is structured as a Lua table named `actions`. Each entry within this table represents a single action and is itself a table containing key-value pairs that define its properties. The general structure for each action is as follows:

```lua
{
	id          = "UNIQUE_ACTION_ID",
	name 		= "Display Name",
	description = "In-game description",
	sprite 		= "path/to/sprite.png",
	type 		= ACTION_TYPE_ENUM, -- e.g., ACTION_TYPE_DRAW_MANY, ACTION_TYPE_MODIFIER, ACTION_TYPE_PROJECTILE
	spawn_level                       = "level_list", -- Comma-separated string of levels where this action can spawn
	spawn_probability                        = "probability_list", -- Comma-separated string of probabilities for each level
	mana = number, -- Mana cost to use the action
	-- Optional fields like custom_xml_file, action function, etc.
	action 		= function()
		-- Lua code defining the action's effect
	end,
},
```

Key fields observed in the samples include:

*   **`id`**: A unique string identifier for the action.
*   **`name`**: The human-readable name of the action displayed in the game.
*   **`description`**: A brief explanation of the action's effect.
*   **`sprite`**: The path to the graphical asset used for the action's icon.
*   **`type`**: An enumeration indicating the category of the action (e.g., drawing more cards, modifying projectiles, spawning projectiles).
*   **`spawn_level`**: A comma-separated string indicating the game levels where this action can potentially appear. An empty string might indicate it's not tied to specific levels or has a special spawning condition.
*   **`spawn_probability`**: A comma-separated string that likely corresponds to the `spawn_level` and dictates the likelihood of the action appearing on that level.
*   **`mana`**: The cost in mana required to activate this action.
*   **`action`**: A Lua function that contains the game logic executed when this action is used. This is where the actual effect of the action is defined.
*   **`custom_xml_file`**: An optional field that points to an XML file defining custom entities or effects associated with the action.

## Key Patterns

Several patterns emerge from the sampled content:

*   **Categorization by Type**: Actions are broadly categorized by their `type`. Common types observed include:
    *   `ACTION_TYPE_DRAW_MANY`: Actions that cause the player to draw additional cards.
    *   `ACTION_TYPE_MODIFIER`: Actions that alter existing projectile properties or wand behavior.
    *   `ACTION_TYPE_PROJECTILE`: Actions that directly spawn a projectile.
*   **Modifier Effects**: Many `ACTION_TYPE_MODIFIER` entries modify global variables or properties of the current wand context (`c`). Examples include `c.spread_degrees`, `c.bounces`, `c.damage_projectile`, `c.gore_particles`, and `c.fire_rate_wait`.
*   **Projectile Spawning**: `ACTION_TYPE_PROJECTILE` actions typically use the `add_projectile()` function, passing the path to an XML entity file that defines the projectile's behavior.
*   **Spawn Logic**: The `spawn_level` and `spawn_probability` fields suggest a system for controlling the availability and rarity of actions across different stages of the game. The specific format of these strings (e.g., `"0,1,2,3,4,5,6,7,8,9,10,11"`) implies a mapping to game levels.
*   **Lua Functions for Logic**: The core functionality of each action is implemented within its `action` function, allowing for dynamic and complex effects.
*   **Comments and IDs**: Comments often follow the `spawn_level` and `spawn_probability` lines, reiterating the action's ID, which aids in readability and debugging.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`BURST_2` (from first 100 lines)**:
    ```lua
    {
        id          = "BURST_2",
        name 		= "Burst (2)",
        description = "Draw 2 more actions",
        sprite 		= "data/ui_gfx/gun_actions/burst_2.png",
        type 		= ACTION_TYPE_DRAW_MANY,
        spawn_level                       = "0,1,2,3,4,5,6,7,8,9,10,11", -- BURST_2
        spawn_probability                        = "1,10,1,1,1,1,1,1,1,1,1,1", -- BURST_2
        mana = 0,
        action 		= function()
            draw_actions( 2, true )
        end,
    },
    ```
    This entry defines a "Burst (2)" action. It's of type `ACTION_TYPE_DRAW_MANY`, meaning it causes the player to draw 2 additional actions. It has a mana cost of 0 and is available across all spawn levels with a specific probability distribution.

2.  **`DAMAGE` (from lines 190-240)**:
    ```lua
    {
        id          = "DAMAGE",
        name 		= "Damage",
        description = "Extra projectile damage and gore",
        sprite 		= "data/ui_gfx/gun_actions/damage.png",
        type 		= ACTION_TYPE_MODIFIER,
        spawn_level                       = "0,1,2,3,4,5,6,7,8,9,10,11", -- DAMAGE
        spawn_probability                        = "1,1,1,1,1,1,1,1,1,1,1,1", -- DAMAGE
        mana = 5,
        custom_xml_file = "data/entities/misc/custom_cards/damage.xml",
        action 		= function()
            c.damage_projectile = c.damage_projectile + 0.4
            c.gore_particles    = c.gore_particles + 5
            c.fire_rate_wait    = c.fire_rate_wait + 5
        end,
    },
    ```
    This is a `ACTION_TYPE_MODIFIER` that increases projectile damage, gore particle count, and fire rate wait time. It also references a `custom_xml_file`, suggesting it might have additional visual or behavioral effects beyond what's directly coded in the Lua function.

3.  **`LIGHTNING` (from lines 1662-1712)**:
    ```lua
    {
        id          = "LIGHTNING",
        name 		= "Lightning",
        description = "A bolt of 120 million volts!",
        sprite 		= "data/ui_gfx/gun_actions/lightning.png",
        type 		= ACTION_TYPE_PROJECTILE,
        spawn_level                       = "0,1,2,3,4,5,6,7,8,9,10,11", -- LIGHTNING
        spawn_probability                        = "1,1,1,1,1,1,1,1,1,1,1,1", -- LIGHTNING
        mana = 70,
        custom_xml_file = "data/entities/misc/custom_cards/electric_charge.xml",
        action 		= function()
            add_projectile("data/entities/projectiles/deck/lightning.xml")
            c.fire_rate_wait = c.fire_rate_wait + 50
            shot_effects.recoil_knockback = 180.0
        end,
    },
    ```
    This action is of type `ACTION_TYPE_PROJECTILE`. When used, it spawns a "lightning" projectile defined by an XML file. It also applies a significant fire rate delay and recoil knockback.

## Reference

This file contains 2390 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/_gun_actions_unlimited.lua).

---