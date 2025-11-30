---
title: Boss Wizard State Management
category: entities
---

# Boss Wizard State Management

This document details the Lua script responsible for managing the state and attack patterns of the Boss Wizard entity in Noita. It dictates which attacks the wizard uses based on its current mode and internal state.

## Core Functionality

The `shot` function is the primary driver for the Boss Wizard's behavior. It's triggered by an in-game event (likely related to the wizard's actions or state changes) and dynamically modifies the `AnimalAIComponent` to control its attacks.

### Key Components Accessed

*   **`VariableStorageComponent` (boss_wizard_state):** Stores the current internal state of the wizard (0-4), cycling through different attack phases.
*   **`VariableStorageComponent` (boss_wizard_mode):** Determines the overall behavior mode of the wizard (e.g., sequential attacks, random attacks, disabling attacks).
*   **`AnimalAIComponent`:** The core AI component that holds attack-related properties like the entity file for ranged attacks and the frame delay between attacks.

### Attack Modes

The script defines three primary attack modes:

*   **Mode 0 (Sequential):** The wizard cycles through its attacks in a predefined order (0, 1, 2, 3, 4).
*   **Mode 1 (Random):** The wizard selects attacks randomly from its available pool.
*   **Mode 2 (Disabled):** All ranged attacks are disabled.

### Attack States and Associated Files

The `state` variable (0-4) within `boss_wizard_state` determines the specific attack to be used. The following table outlines the state, its typical behavior, and the associated entity file for the ranged attack.

| State | Behavior Description