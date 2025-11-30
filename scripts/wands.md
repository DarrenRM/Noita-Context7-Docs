---
title: wands
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/procedural/wands.lua
---

# wands

This file, `wands.lua`, defines the properties and characteristics of various wands available in the game Noita. Wands are the primary weapons players use, and their behavior is determined by the spells they contain and their inherent properties. This file acts as a configuration or data definition for these items, dictating their visual representation, firing mechanics, and how they interact with the game's spell system. It is a crucial component for procedural generation of wands and for defining their base attributes.

## File Structure

The `wands.lua` file is structured as a Lua table named `wands`. This table contains a list of individual wand definitions, each enclosed in curly braces `{}`. Each wand definition is itself a table of key-value pairs, where the keys are strings representing the wand's properties and the values are the corresponding data (numbers, strings, or booleans).

The general pattern for each wand entry is:

```lua
{
  name = "Wand Name",
  file = "path/to/wand/sprite.png",
  grip_x = number,
  grip_y = number,
  tip_x = number,
  tip_y = number,
  fire_rate_wait = number,
  actions_per_round = number,
  shuffle_deck_when_empty = number, -- Typically 0 or 1
  deck_capacity = number,
  spread_degrees = number,
  reload_time = number,
  -- ... other potential properties
},
```

-   **`name`**: A string representing the display name of the wand.
-   **`file`**: A string indicating the path to the sprite file used for the wand's visual representation.
-   **`grip_x`, `grip_y`**: Numbers defining the X and Y coordinates for the wand's grip point, likely used for animation and player interaction.
-   **`tip_x`, `tip_y`**: Numbers defining the X and Y coordinates for the wand's tip, likely used for projectile origin.
-   **`fire_rate_wait`**: A number representing the delay (in game ticks or frames) between shots. A value of 0 might indicate rapid firing or a special firing mode.
-   **`actions_per_round`**: A number indicating how many spells are cast per "round" of firing.
-   **`shuffle_deck_when_empty`**: A boolean-like number (0 for false, 1 for true) that determines if the wand's spell deck is shuffled when it runs out of spells.
-   **`deck_capacity`**: A number representing the maximum number of spells the wand can hold in its "deck".
-   **`spread_degrees`**: A number indicating the base spread angle in degrees for projectiles fired by this wand.
-   **`reload_time`**: A number representing the time it takes for the wand to reload, likely in game ticks or frames.

## Key Patterns

Several patterns and categories emerge from the sampled data:

*   **Naming Conventions**: Wands often have descriptive names like "Spread staff", "Burst wand", "Explosion staff", "Beam wand", and "Bolt stick". These names generally hint at their primary firing behavior or effect.
*   **Sprite Files**: The `file` attribute consistently points to images within `data/items_gfx/wands/`, suggesting a systematic naming convention for wand sprites, likely `wand_XXXX.png` where XXXX is a numerical index.
*   **Numerical Properties**: Most properties are represented by numerical values. `shuffle_deck_when_empty` appears to be a binary flag (0 or 1).
*   **Core Mechanics**: Properties like `fire_rate_wait`, `actions_per_round`, `deck_capacity`, and `spread_degrees` are fundamental to defining a wand's combat effectiveness and playstyle.
*   **Variations**: Even wands with similar names (e.g., "Burst staff" vs. "Burst wand") can have different numerical values for their properties, indicating distinct variations of a general type.
*   **Indexing**: The `file` attribute suggests a sequential indexing of wands, with numbers like `wand_0000.png`, `wand_0122.png`, `wand_0308.png`, and `wand_0607.png` appearing in the samples. This implies a large number of pre-defined wand types.

## Sample Entries

Here are a few representative examples from the sampled content:

**Example 1: "Spread staff"**
```lua
  {
  name = "Spread staff",
  file = "data/items_gfx/wands/wand_0000.png",
  grip_x = 2,
  grip_y = 5,
  tip_x = 21,
  tip_y = 5,
  fire_rate_wait = 4,
  actions_per_round = 1,
  shuffle_deck_when_empty = 0,
  deck_capacity = 5,
  spread_degrees= 1,
  reload_time = 1,
  },
```
This entry defines a "Spread staff" with a moderate `fire_rate_wait` of 4, casting 1 action per round. It has a `deck_capacity` of 5 and a `spread_degrees` of 1, indicating it will fire projectiles with a slight spread. `shuffle_deck_when_empty` is 0, meaning its deck won't shuffle when empty.

**Example 2: "Explosion staff"**
```lua
  {
  name = "Explosion staff",
  file = "data/items_gfx/wands/wand_0122.png",
  grip_x = 3,
  grip_y = 7,
  tip_x = 21,
  tip_y = 7,
  fire_rate_wait = 4,
  actions_per_round = 1,
  shuffle_deck_when_empty = 0,
  deck_capacity = 5,
  spread_degrees= 2,
  reload_time = 0,
  },
```
This "Explosion staff" has a similar `fire_rate_wait` and `actions_per_round` to the "Spread staff" but a larger `spread_degrees` of 2. Notably, its `reload_time` is 0, suggesting it might have a very fast reload or a special firing mechanic that bypasses standard reloading.

**Example 3: "Bolt stick"**
```lua
  {
  name = "Bolt stick",
  file = "data/items_gfx/wands/wand_0308.png",
  grip_x = 1,
  grip_y = 3,
  tip_x = 9,
  tip_y = 3,
  fire_rate_wait = 3,
  actions_per_round = 2,
  shuffle_deck_when_empty = 0,
  deck_capacity = 0,
  spread_degrees= 2,
  reload_time = 0,
  },
```
The "Bolt stick" has a faster `fire_rate_wait` of 3 and casts 2 actions per round. It has a `deck_capacity` of 0, which is unusual and might imply it functions differently or relies on a specific spell interaction. It also has a `spread_degrees` of 2 and a `reload_time` of 0.

## Reference

This file contains 14003 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/gun/procedural/wands.lua).

---