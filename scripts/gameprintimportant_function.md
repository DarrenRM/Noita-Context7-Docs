---
title: GamePrintImportant Function
category: scripts
---

# GamePrintImportant Function

This documentation describes the `GamePrintImportant` function, a utility for displaying important messages within the Noita game environment. It's primarily used for debugging and providing in-game feedback.

## Purpose

The `GamePrintImportant` function is designed to output messages to the game's console or a designated display area, highlighting them as "important." This is useful for:

*   **Debugging:** Tracking game state, variable values, or the execution flow of scripts.
*   **Player Feedback:** Informing the player about significant events or status changes that might not be immediately obvious through visual cues.

## Usage

The function takes one or more string arguments. The first argument is typically the main message, and subsequent arguments can be used for additional details or context.

### Syntax

```lua
GamePrintImportant( message1, message2, ... )
```

### Parameters

*   `message1` (string): The primary message to be displayed.
*   `message2` (string, optional): Additional text to accompany the primary message.
*   `...` (string, optional): Further optional string arguments for more detailed messages.

## Examples

Here are a few examples demonstrating how to use `GamePrintImportant`:

### Example 1: Basic Message

```lua
-- Displays "Entered mountain" as the main message and "That's cool" as additional info.
GamePrintImportant( "Entered mountain", "That's cool" )
```

### Example 2: Status Update

```lua
-- Displays "Extra hp" as the main message and "That's cool" as additional info.
GamePrintImportant( "Extra hp", "That's cool" )
```

### Example 3: Multiple Arguments

```lua
-- Displays "Player position:", "X: 100", "Y: 250"
GamePrintImportant( "Player position:", "X: 100", "Y: 250" )
```

## Key Attributes/Elements

*   **Simplicity:** The function is straightforward to use, requiring only string arguments.
*   **Clarity:** Designed to make important messages stand out.
*   **Debugging Tool:** An essential function for modders to understand and troubleshoot their scripts.
*   **In-Game Feedback:** Can be leveraged to provide subtle but important information to the player.