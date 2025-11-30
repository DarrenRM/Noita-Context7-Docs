---
title: Boss Limbs Update Logic
category: entities
---

# Boss Limbs Update Logic

This document details the Lua script responsible for the behavior and attack patterns of the "Boss Limbs" entity in Noita. It manages the boss's movement states, attack phases, and visual animations.

## Core Logic States

The boss can exist in several distinct states, controlled by the `LimbBossComponent`. These states dictate its general behavior.

*   `MoveAroundNest = 0`: The boss moves around its designated area.
*   `FollowPlayer = 1`: The boss actively pursues the player.
*   `Escape = 2`: The boss attempts to flee from the player.
*   `DontMove = 3`: The boss remains stationary.

## Attack Phases

The boss cycles through various attack patterns, each defined by a `phase` function. These functions control the sequence of actions, including exposing weak spots, shooting projectiles, and spawning minions.

### `phase0()`
*   Initializes with `FollowPlayer` state.
*   Waits for 5 minutes (300 frames).
*   Transitions to a randomly chosen phase.

### `phase1()`
*   Initializes with `DontMove` state.
*   Exposes weak spot, performs `circleshot` three times with short pauses.
*   Keeps weak spot exposed for 3 * 80 frames.
*   Hides weak spot.
*   Transitions to a randomly chosen phase.

### `phase2()`
*   Initializes with `FollowPlayer` state.
*   Spawns a minion, waits 30 frames.
*   Spawns another minion, waits 100 frames.
*   Transitions to a randomly chosen phase.

### `phase3()`
*   Initializes with `FollowPlayer` state.
*   Initiates a chase sequence (`prepare_chase`, `chase_start`).
*   Waits for 80 frames.
*   Stops the chase (`chase_stop`).
*   Transitions to `phase1`.

### `phase4()`
*   Initializes with `DontMove` state.
*   Exposes weak spot, performs `homingshot` twice with pauses.
*   Hides weak spot.
*   Transitions to `phase0`.

## Key Helper Functions

These functions implement specific actions and behaviors for the boss.

### Projectile Attacks

*   `circleshot()`: Fires a spread of 8 projectiles in a circle around the boss.
*   `homingshot()`: Fires a single homing projectile.

### Minion Spawning

*   `spawn_minion()`: Spawns a `slimeshooter_boss_limbs` entity if fewer than 2 are currently active. The spawned minion receives a random initial velocity.

### Animation Control

*   `set_main_animation(current_name, next_name)`: Sets the primary sprite animation.
*   `animate_random_detail()`: Randomly animates one of the boss's detail sprites.
*   `set_details_hidden(is_hidden)`: Controls the visibility and animation of the boss's detail sprites.
*   `set_detail_animation(current_name)`: Sets the animation for detail sprites.
*   `animate_sprite(sprite, current_name, next_name)`: Plays a specific sprite animation.
*   `animate_sprite_simple(sprite, current_name, next_name)`: Sets a sprite animation directly.

### Combat Mechanics

*   `expose_weak_spot()`: Makes the boss's weak spot vulnerable, enabling specific hitboxes and playing an "open" animation.
*   `hide_weak_spot()`: Closes the weak spot, disabling weak hitboxes and returning to a default animation.
*   `set_hitboxes_weak(weak_spot_exposed)`: Enables or disables specific hitbox components based on the weak spot's state.

### State Management

*   `set_logic_state(state)`: Updates the boss's current behavior state in the `LimbBossComponent`.

### Death Sequence

*   `check_death()`: Monitors the boss's HP. If HP drops to 0 or below, it triggers a death animation, spawns particles, disables attack limbs, and marks the boss as dead. It also applies a persistent flag.
*   `boss_wait(frames)`: A utility function that waits for a specified number of frames, checking for death at the beginning and end of the wait.

## Initialization

The script initializes the boss with:
*   Weak hitboxes disabled.
*   Idle animation set.
*   Details visible.
*   The state machine begins with `phase0`.

## Coroutine Loop

An `async_loop` continuously runs the boss's state machine. It checks for death and executes the current `state()` function. A small `wait(1)` is included to prevent the loop from getting stuck if a state doesn't inherently include a wait.