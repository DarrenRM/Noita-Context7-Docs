---
title: gun_actions_petri
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/gun_actions_petri.lua
---

# gun_actions_petri

This file, `gun_actions_petri.lua`, defines a collection of "actions" that can be applied to a player's gun in the game Noita. These actions represent various modifiers, projectile effects, and utility functions that alter how the gun fires and what its projectiles do. They are essentially the building blocks for creating diverse and powerful gun combinations within the game's procedural generation system. This file is crucial for defining the gameplay mechanics related to gun customization and combat.

## File Structure

The file is structured as a Lua script that defines a global table named `actions`. Each entry within this `actions` table is itself a table representing a single gun action. These action tables share a consistent structure, containing key-value pairs that describe the action's properties and behavior.

The common keys observed are:

*   **`id`**: A unique string identifier for the action.
*   **`name`**: A human-readable name for the action, displayed in-game.
*   **`description`**: A brief explanation of what the action does.
*   **`sprite`**: The file path to the icon used for this action in the game's UI.
*   **`type`**: A constant indicating the category of the action (e.g., `ACTION_TYPE_DRAW_MANY`, `ACTION_TYPE_PROJECTILE`, `ACTION_TYPE_MODIFIER`, `ACTION_TYPE_OTHER`).
*   **`spawn_level`**: A comma-separated string of level indices where this action can potentially spawn.
*   **`spawn_probability`**: A comma-separated string of probabilities corresponding to the `spawn_level` entries, determining how likely the action is to appear on a given level.
*   **`mana`**: The mana cost associated with using this action.
*   **`max_uses`**: The maximum number of times this action can be used before it's depleted (if applicable).
*   **`custom_xml_file`**: An optional field pointing to a custom XML file that might define additional effects or properties.
*   **`action`**: A Lua function that defines the specific game logic executed when this action is triggered. This function often modifies global game state variables (prefixed with `c.`) or calls other game functions like `add_projectile`.

Comments (`--`) are used extensively for explanations and to mark specific entries or sections. Some entries are commented out using `--[[ ... ]]--`, indicating they are disabled or experimental.

## Key Patterns

Several patterns emerge from the sampled content:

*   **Categorization by `type`**: Actions are broadly categorized by their `type`.
    *   `ACTION_TYPE_DRAW_MANY`: These actions typically draw additional "cards" or actions, often with modifiers like increased spread.
    *   `ACTION_TYPE_PROJECTILE`: These actions add specific projectiles to the gun's firing repertoire, often referencing `.xml` files for projectile definitions.
    *   `ACTION_TYPE_MODIFIER`: These actions directly alter the properties of the gun or its projectiles, such as changing material or adding recoil.
    *   `ACTION_TYPE_OTHER`: These actions provide utility effects, like the "X-RAY" action for seeing through walls.
*   **Spawn Logic**: The `spawn_level` and `spawn_probability` fields work in tandem to control where and how often an action appears in the game. The probabilities are often higher for earlier levels or specific levels where a particular effect might be more relevant.
*   **Lua Functions for Logic**: The core behavior of each action is defined by a Lua function assigned to the `action` key. These functions interact with the game's internal state and functions.
*   **Projectile Spawning**: Many actions involve calling `add_projectile()` or similar functions, passing a path to an XML file that defines the projectile's behavior, appearance, and damage.
*   **Modifier Effects**: Modifier actions often directly manipulate variables prefixed with `c.` (likely representing the current gun's properties) or `shot_effects`.
*   **Comments for Context**: Comments are used to associate `spawn_level` and `spawn_probability` values with specific action IDs, aiding in understanding their intended distribution.

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
        spawn_probability                        = "1,10,10,1,1,1,1,1,1,1,1,1", -- BURST_2
        mana = 0,
        action 		= function()
            draw_actions( 2, true )
        end,
    },
    ```
    This entry defines a "Burst (2)" action. It's of type `ACTION_TYPE_DRAW_MANY`, meaning it draws more actions. It has a mana cost of 0 and is designed to be available across most levels, with a higher probability in levels 1 and 2. The `action` function simply calls `draw_actions(2, true)`, which likely adds two more actions to the player's hand.

2.  **`BERSERK_FIELD` (from lines 503-553)**:
    ```lua
    {
        id          = "BERSERK_FIELD",
        name 		= "Berserk field",
        description = "Berserks everyone!",
        sprite 		= "data/ui_gfx/gun_actions/berserk_field.png",
        type 		= ACTION_TYPE_PROJECTILE,
        spawn_level                       = "0,1,2,3,4,5,6,7,8,9,10,11", -- BERSERK_FIELD
        spawn_probability                        = "1,1,1,1,1,1,1,1,1,1,1,1", -- BERSERK_FIELD
        mana = 30,
        max_uses = 15,
        action 		= function()
            add_projectile("data/entities/projectiles/deck/berserk_field.xml")
            c.fire_rate_wait = c.fire_rate_wait + 15
        end,
    },
    ```
    This action, "Berserk field," is of type `ACTION_TYPE_PROJECTILE`. It costs 30 mana and has a maximum of 15 uses. When activated, it adds a "berserk field" projectile (defined by `data/entities/projectiles/deck/berserk_field.xml`) and increases the gun's `fire_rate_wait`. This suggests it creates an area-of-effect that causes enemies to attack each other.

3.  **`MINE` (from lines 1670-1720)**:
    ```lua
    {
        id 			= "MINE",
        name 		= "Explosive crystal",
        description = "An explosive crystal that detonates when collided with.",
        sprite 		= "data/ui_gfx/gun_actions/mine.png",
        type 		= ACTION_TYPE_PROJECTILE,
        spawn_level	           = "0,1,2,3,4,5,6,7,8,9,10,11", -- MINE
        spawn_probability	           = "1,1,20,1,1,1,1,1,1,1,1,1", -- MINE
        mana = 20,
        max_uses	= 30,
        action 		= function()
            add_projectile("data/entities/projectiles/deck/mine.xml")
            c.fire_rate_wait = c.fire_rate_wait + 30
            c.child_speed_multiplier = c.child_speed_multiplier * 0.75
            c.speed_multiplier = c.speed_multiplier * 0.75
            shot_effects.recoil_knockback = 60.0
        end,
    },
    ```
    The "Explosive crystal" action is a `ACTION_TYPE_PROJECTILE`. It has a moderate mana cost and a good number of uses. Its spawn probability is notably high in level 2. The action adds a "mine" projectile and applies several modifiers: increased `fire_rate_wait`, reduced speed multipliers for the projectile and its children, and a significant `recoil_knockback`. This action creates a deployable explosive.

## Reference

This file contains 2659 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/gun_actions_petri.lua).

---