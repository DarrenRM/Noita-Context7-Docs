---
title: Coroutine Utilities
category: scripts
---

# Coroutine Utilities

This library provides essential functions for managing coroutines in Noita, enabling asynchronous operations and timed delays. It's crucial for creating dynamic and responsive modded gameplay.

## Core Concepts

*   **Coroutines:** Lightweight threads that allow for cooperative multitasking. They can pause their execution (`yield`) and be resumed later.
*   **Signals:** Named events that coroutines can wait for. When a signal is triggered, all coroutines waiting on that signal are resumed.
*   **Time-based Waiting:** Coroutines can be set to resume after a specific number of game frames.

## Key Functions

### `wait(frames)`

Pauses the current coroutine for a specified number of game frames.

*   **`frames`** (number): The number of frames to wait.
*   **Returns:** The result of `coroutine.resume` when the coroutine is resumed.
*   **Error:** Throws an error if called from the main thread (which cannot yield).

### `wake_up_waiting_threads(frames_delta)`

Advances the game's internal timer and resumes any coroutines that have met their waiting conditions. This function should be called once per game logic update.

*   **`frames_delta`** (number): The amount of time (in frames) that has passed since the last call.

### `wait_signal(signalName)`

Pauses the current coroutine until a specific signal is triggered.

*   **`signalName`** (string): The name of the signal to wait for.
*   **Returns:** The result of `coroutine.resume` when the coroutine is resumed.
*   **Error:** Throws an error if called from the main thread.

### `wait_signal_callback(signalName, callback)`

Pauses the current coroutine until a specific signal is triggered, and also registers a callback function to be executed when the signal is received.

*   **`signalName`** (string): The name of the signal to wait for.
*   **`callback`** (function): A function to execute when the signal is triggered.
*   **Returns:** The result of `coroutine.resume` when the coroutine is resumed.
*   **Error:** Throws an error if called from the main thread.

### `signal(signalName)`

Triggers a specific signal, resuming all coroutines that are currently waiting on it. If callbacks were registered with `wait_signal_callback`, they will also be executed.

*   **`signalName`** (string): The name of the signal to trigger.

### `signal_2params(signalName, a, b)`

Triggers a specific signal, resuming all coroutines that are currently waiting on it, and passing two additional parameters to the resumed coroutines.

*   **`signalName`** (string): The name of the signal to trigger.
*   **`a`**: The first parameter to pass.
*   **`b`**: The second parameter to pass.

### `async(func)`

Creates and immediately starts a new coroutine to execute the provided function.

*   **`func`** (function): The function to run in a new coroutine.
*   **Returns:** The result of the initial `coroutine.resume` call.

### `async_loop(func)`

Creates and immediately starts a new coroutine that will repeatedly execute the provided function in an infinite loop.

*   **`func`** (function): The function to run repeatedly in the coroutine.
*   **Returns:** The result of the initial `coroutine.resume` call.

## Internal State

The library uses internal tables to manage coroutine states:

*   **`WAITING_ON_TIME`**: Stores coroutines waiting for a specific time. Indexed by coroutine, value is the wakeup time.
*   **`WAITING_ON_SIGNAL`**: Stores coroutines waiting for signals. Indexed by signal name, value is a list of coroutines.
*   **`WAITING_ON_SIGNAL_CALLBACK`**: Stores callback functions for signals. Indexed by signal name, value is a list of callback functions.
*   **`CURRENT_TIME`**: Tracks the total elapsed game time in frames.