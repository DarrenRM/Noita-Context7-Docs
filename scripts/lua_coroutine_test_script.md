---
title: Lua Coroutine Test Script
category: scripts
---

---

# Lua Coroutine Test Script

This script demonstrates the basic usage of coroutines in Noita for asynchronous operations. It utilizes the `async` and `wait` functions from the `coroutines.lua` library.

## Core Functionality

The script defines an asynchronous function that runs in a loop.

### Asynchronous Function (`async`)

-   **Purpose**: Executes a function asynchronously, allowing other game processes to continue while this function is running.
-   **Structure**: Uses `async(function() ... end)` to define the asynchronous block.

### Loop (`while true`)

-   **Purpose**: Creates an infinite loop to continuously execute the coroutine's logic.

### Counter (`i`)

-   **Purpose**: A simple integer variable used to track the number of times the coroutine has resumed.
-   **Initialization**: Starts at `0`.
-   **Increment**: Incremented by `1` each time the coroutine resumes.

### Output (`print`)

-   **Purpose**: Logs messages to the console indicating when the coroutine has resumed and the current value of the counter.
-   **Format**: `"resumed " .. i`

### Wait (`wait`)

-   **Purpose**: Pauses the execution of the current coroutine for a specified number of frames.
-   **Duration**: `60` frames. This means the `print` statement and counter increment will occur every 60 frames.

## Example Usage

When this script is loaded in Noita, it will:

1.  Start an asynchronous process.
2.  Enter an infinite loop.
3.  Print "resumed 0" to the console.
4.  Wait for 60 frames.
5.  Print "resumed 1" to the console.
6.  Wait for 60 frames.
7.  ...and so on, indefinitely.

This is a fundamental example for understanding how to create non-blocking operations and timed events within Noita mods.