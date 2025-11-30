---
title: Daily Wand Generation Configuration
category: scripts
---

# Daily Wand Generation Configuration

This script configures the generation of a daily wand in Noita. It utilizes a pre-existing function `generate_daily_wand` to create a wand with specific parameters.

## Key Parameters for `generate_daily_wand`

The `generate_daily_wand` function is called with the following arguments:

*   **`80`**: This likely represents the **wand's base mana**. A higher value allows for more complex and powerful spell combinations.
*   **`4`**: This parameter probably dictates the **maximum number of spells** that can be on the wand. A higher number allows for more diverse spell effects.
*   **`false`**: This boolean value likely controls whether the wand is **guaranteed to have a specific spell or property**. `false` suggests a more randomized or standard generation.

## Related Generation Function (Commented Out)

The script also includes a commented-out call to `generate_gun`:

```lua
-- generate_gun( 40, 2, false )
```

This suggests that `generate_gun` is another function for generating weapons, potentially with different characteristics or for different purposes. The parameters `40`, `2`, and `false` would similarly influence its generation.