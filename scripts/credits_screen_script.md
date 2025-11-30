---
title: Credits Screen Script
category: scripts
---

# Credits Screen Script

This script handles the display of the game's credits sequence in Noita. It utilizes asynchronous functions to manage the timing and display of different credit sections.

## Core Functionality

The script orchestrates the display of credit text by:

*   Initializing a GUI element.
*   Sequentially displaying different categories of credits (e.g., "NOITA", "PROGRAMMING BY", "MUSIC BY").
*   Pausing between each credit section for a specified duration.
*   Destroying the GUI element and cleaning up when the credits are finished.

## Key Functions and Elements

### `wait_seconds( seconds )`

A helper function to pause the execution of an asynchronous function for a given number of seconds.

```lua
function wait_seconds( seconds )
	wait( seconds * 60 ) -- Noita's wait function uses frames, so multiply by 60 for seconds.
end
```

### `async(function() ... end)`

This function is used to run code asynchronously, allowing the credits to be displayed without blocking the main game loop.

### `GuiCreate()`

Initializes a new GUI element to be used for displaying text.

### `GuiLayoutBeginVertical( gui, x, y )` and `GuiLayoutEnd( gui )`

These functions define a vertical layout for GUI elements. Text elements added between these calls will be stacked vertically.

### `GuiTextCentered( gui, x, y, text )`

Displays a given `text` string centered within the current GUI layout.

### `gui_frame_fn`

A function variable that holds the current rendering logic for the credits GUI. This allows the displayed content to change over time.

### `async_loop(function() ... end)`

This function runs continuously, handling the frame-by-frame updates for the GUI. It ensures that the `gui_frame_fn` is called to render the current credit section.

## Credit Sections

The script defines several distinct credit sections, each displayed for a set duration. These include:

*   **Game Title:** "NOITA"
*   **Development Team:** "A GAME BY", "PROGRAMMING BY", "DESIGN BY", "(SOME) GRAPHICS BY", "(OTHER) GRAPHICS BY"
*   **Audio Credits:** "MUSIC BY", "SOUND DESIGN BY"
*   **Other Contributors:** "TESTERS BY", "TRANSLATION BY"
*   **Conclusion:** "THE END"

Each section is displayed with a `wait_seconds(2)` pause before transitioning to the next.

## Cleanup

Upon completion of the credits sequence:

*   `GuiDestroy( gui )` is called to remove the GUI element.
*   `gui_frame_fn` is set to `nil` to stop rendering.
*   `gui` is set to `nil` for garbage collection.
*   `GameRemoveFlagRun( "ending_no_game_over_menu" )` is called, likely to re-enable the game over menu.
*   `EntityKill( GetUpdatedEntityID() )` removes the entity responsible for running the credits script.