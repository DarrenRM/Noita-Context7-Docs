---
title: gun_actions_limited
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/gun_actions_limited.lua
---

# gun_actions_limited

This file, `gun_actions_limited.lua`, defines a collection of "actions" that can be applied to guns in the game Noita. These actions represent various modifiers, special effects, or projectile behaviors that players can acquire and equip. They are essentially the game's way of defining the unique properties and abilities of different cards or spells that affect how a gun fires. This file is crucial for the game's combat system, as it dictates the variety of offensive and utility options available to the player.

## File Structure

The file defines a global Lua table named `actions`. Each entry within this `actions` table is itself a table representing a single gun action. These action tables share a consistent structure, containing the following key-value pairs:

*   **`id`**: A unique string identifier for the action (e.g., `"BURST_2"`, `"CHAOS_POLYMORPH_FIELD"`).
*   **`name`**: A human-readable name for the action, displayed in the game's UI (e.g., `"Burst (2)"`, `"Chaos polymorph field"`).
*   **`description`**: A brief text explaining the effect of the action.
*   **`sprite`**: The file path to the image asset used for the action's icon in the UI.
*   **`type`**: A constant indicating the general category of the action. Common types observed include:
    *   `ACTION_TYPE_DRAW_MANY`: Actions that draw additional cards/actions.
    *   `ACTION_TYPE_PROJECTILE`: Actions that spawn specific projectiles.
    *   `ACTION_TYPE_MODIFIER`: Actions that modify existing projectile properties or gun behavior.
*   **`spawn_level`**: A comma-separated string of level indices where this action can potentially spawn.
*   **`spawn_probability`**: A comma-separated string of probabilities corresponding to each level in `spawn_level`, indicating how likely the action is to appear.
*   **`mana`**: The mana cost associated with using this action.
*   **`max_uses`**: (Optional) The maximum number of times this action can be used before it's depleted.
*   **`custom_xml_file`**: (Optional) A file path to an XML file that defines custom behavior or entities associated with this action.
*   **`action`**: A Lua function that defines the specific game logic executed when this action is activated. This function often modifies global game state variables (like `c` for current gun properties) or calls other game functions (like `draw_actions` or `add_projectile`).

Comments (`--`) are used extensively for explanations and to mark specific entries.

## Key Patterns

Several patterns are evident in the sampled data:

*   **Categorization by Effect**: Actions are grouped implicitly by their primary effect. For instance, "Burst" actions are together, "Scatter" actions are together, and "Trail" modifiers are grouped.
*   **Scaling Effects**: Many actions have variations that scale an effect. For example, `BURST_2`, `BURST_3`, and `BURST_4` all draw more actions, with the number increasing. Similarly, `SCATTER_2`, `SCATTER_3`, and `SCATTER_4` increase the scatter effect.
*   **Projectile Spawning**: A significant portion of actions are of `ACTION_TYPE_PROJECTILE`. These actions typically call `add_projectile()` with a specific XML entity path, defining the projectile that will be fired.
*   **Modifier Actions**: Actions of `ACTION_TYPE_MODIFIER` often directly alter properties of the current gun's configuration (represented by the `c` variable). This includes modifying `spread_degrees`, `trail_material`, `damage_projectile`, `fire_rate_wait`, etc.
*   **`spawn_level` and `spawn_probability`**: These fields are consistently present and seem to control the distribution of actions across different game levels. The probabilities often appear to be higher in earlier levels and decrease in later ones for some actions, while others have uniform probabilities.
*   **`custom_xml_file` Usage**: This field is used for more complex actions that require external XML definitions, often for unique projectile behaviors or visual effects.
*   **`action` Function Logic**: The `action` functions are the core of each entry. They demonstrate how game mechanics are implemented through Lua scripting, ranging from simple variable manipulation to complex projectile spawning and effect application.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`BURST_2`**:
    ```lua
    {
        id          = "BURST_2",
        name 		= "Burst (2)",
        description = "Draw 2 more actions",
        sprite 		= "data/ui_gfx/gun_actions/burst_2.png",
        type 		= ACTION_TYPE_DRAW_MANY,
        spawn_level                       = "0,1,2,3,4,5,6,7,8,9,10,11",
        spawn_probability                        = "1,10,10,1,1,1,1,1,1,1,1,1",
        mana = 0,
        action 		= function()
            draw_actions( 2, true )
        end,
    },
    ```
    This entry defines a "Burst (2)" action. It's of type `ACTION_TYPE_DRAW_MANY`, meaning it draws additional cards. When activated, its `action` function calls `draw_actions(2, true)`, which instructs the game to draw 2 more actions for the player. It has a mana cost of 0 and is more likely to spawn in levels 1 and 2.

2.  **`CHAOS_POLYMORPH_FIELD`**:
    ```lua
    {
        id          = "CHAOS_POLYMORPH_FIELD",
        name 		= "Chaos polymorph field",
        description = "Polymorphs everyone to random enemies!",
        sprite 		= "data/ui_gfx/gun_actions/chaos_polymorph_field.png",
        type 		= ACTION_TYPE_PROJECTILE,
        spawn_level                       = "0,1,2,3,4,5,6,7,8,9,10,11",
        spawn_probability                        = "1,1,1,1,1,1,1,1,1,1,1,1",
        mana = 20,
        max_uses = 10,
        action 		= function()
            add_projectile("data/entities/projectiles/deck/chaos_polymorph_field.xml")
            c.fire_rate_wait = c.fire_rate_wait + 15
        end,
    },
    ```
    This action is of type `ACTION_TYPE_PROJECTILE`. Its `action` function calls `add_projectile` to spawn a specific projectile defined by `data/entities/projectiles/deck/chaos_polymorph_field.xml`. This projectile likely causes enemies to polymorph. It also increases the gun's `fire_rate_wait` by 15 and has a mana cost of 20 with a maximum of 10 uses.

3.  **`ACID_TRAIL`**:
    ```lua
    {
        id          = "ACID_TRAIL",
        name 		= "Acid trail",
        description = "Projectiles leave a trail of acid",
        sprite 		= "data/ui_gfx/gun_actions/acid_trail.png",
        type 		= ACTION_TYPE_MODIFIER,
        spawn_level                       = "0,1,2,3,4,5,6,7,8,9,10,11",
        spawn_probability                        = "1,1,1,1,1,1,1,1,1,1,1,1",
        mana = 15,
        custom_xml_file = "data/entities/misc/custom_cards/acid_trail.xml",
        action 		= function()
            c.trail_material = c.trail_material .. "acid,"
            c.trail_material_amount = c.trail_material_amount + 5
        end,
    },
    ```
    This is a `ACTION_TYPE_MODIFIER`. Its `action` function modifies the current gun's properties (`c`). It appends `"acid,"` to the `trail_material` string and increases `trail_material_amount` by 5. This means projectiles fired from a gun with this action will leave an acid trail. It also references a `custom_xml_file` for potentially more detailed effects.

## Reference

This file contains 2659 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/gun_actions_limited.lua).

---