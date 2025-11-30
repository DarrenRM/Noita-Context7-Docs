---
title: Money Drop Modifier (4x)
category: scripts
---

# Money Drop Modifier (4x)

This script modifies the default money drop behavior in Noita, specifically increasing the amount of money dropped upon player death.

## Core Functionality

The primary purpose of this script is to override the default money drop mechanism and ensure a significantly larger amount of currency is generated.

### Key Attributes

*   **`dofile("data/scripts/items/drop_money.lua")`**: This line imports the necessary functions from the base `drop_money.lua` script, which contains the logic for generating money drops.
*   **`function death(...)`**: This function is a hook that Noita calls whenever the player dies.
*   **`do_money_drop(4, true)`**: This is the core modification. It calls the imported `do_money_drop` function with specific arguments:
    *   `4`: This likely represents a multiplier for the base money drop amount. In this case, it quadruples the standard drop.
    *   `true`: This boolean argument might control whether special drop conditions or variations are applied, or it could be related to the type of currency dropped.

## Usage

This script is intended to be placed in the `data/scripts/items/` directory. When active, it will automatically apply its effect whenever the player dies.

## Example

When the player dies, instead of the default amount of gold, they will receive four times that amount.