---
title: Meditation Cube Logic
category: scripts
---

# Meditation Cube Logic

This script defines the behavior of the "Meditation Cube" entity in Noita, which acts as a timed activation mechanism.

## Core Functionality

The primary function of this script is to track player proximity and time spent near the entity to trigger subsequent events.

### Key Attributes & Logic

*   **`meditation_count` Storage:** A read/write variable storage component is used to track the `value_int` representing the meditation progress.
*   **Player Proximity Check:** The script continuously checks for a player unit within a radius of 25 units around the cube's position (with a slight vertical offset).
*   **Countdown Mechanism:**
    *   If a player is near, `meditation_count` is incremented.
    *   If `meditation_count` reaches `18`, the cube fully activates, enabling components tagged with `"enabled_by_meditation"` and disabling those tagged with `"enabled_by_meditation_early"`. The script itself is then disabled.
    *   If `meditation_count` reaches `6`, a "teaser" effect is activated by enabling components tagged with `"enabled_by_meditation_early"`.
*   **Reset Condition:** If the player moves out of range, the `meditation_count` is reset to `0`, and the `"enabled_by_meditation_early"` components are disabled.

### Relevant Tags

*   `"player_unit"`: Used to identify the player entity.
*   `"enabled_by_meditation"`: Components that are enabled upon full meditation completion.
*   `"enabled_by_meditation_early"`: Components that are enabled during the "teaser" phase of meditation.

```lua
-- Example of how the script might be attached to an entity
-- This is illustrative and not part of the provided script file.

-- In an entity's .xml file:
-- <Entity tags="meditation_cube">
--   <LuaComponent script_path="data/scripts/buildings/meditation_cube.lua" />
--   <VariableStorageComponent name="meditation_count" />
--   <SomeOtherComponent tag="enabled_by_meditation" />
--   <AnotherComponent tag="enabled_by_meditation_early" />
-- </Entity>
```