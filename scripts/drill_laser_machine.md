---
title: Drill Laser Machine
category: scripts
---

# Drill Laser Machine

This document details the functionality of the Drill Laser machine, a scripted entity in Noita that utilizes electricity and a fuel source to activate laser emitters.

## Core Functionality

The Drill Laser machine operates based on two primary conditions:

1.  **Activation:** The machine turns ON when it receives an electrical jolt *and* a fuel source is detected within its area.
2.  **Deactivation:** The machine turns OFF when the fuel source is depleted.

## Key Components and Logic

### `set_lasers(on)` Function

This function controls the state of the laser emitters and associated visual effects.

*   **`on` (boolean):** Determines whether the lasers should be activated (`true`) or deactivated (`false`).
*   **Laser Emitters:** Iterates through child entities tagged with `"drill_laser"` and toggles their `LaserEmitterComponent`'s `is_emitting` property.
*   **Laser FX:** Enables or disables components tagged with `"laser_fx"` based on the `on` state.
*   **Fuel Igniter:** Toggles the `"igniter"` component of the main entity, likely for visual feedback or a related mechanic.

### `electricity_receiver_switched(on)` Function

This function is triggered by electrical input to the machine.

*   **`on` (boolean):** Represents the electrical state. If `false` (no electricity), the function returns early, as only fuel depletion turns off the lasers.
*   **Fuel Check:** Retrieves the `is_fueled` variable from the `VariableStorageComponent`.
*   **Laser Activation:** Calls `set_lasers()` with the current fuel status (`on` variable, which is updated by fuel presence).

### `material_area_checker_success(pos_x, pos_y)` Function

This function is called when the `MaterialAreaCheckerComponent` detects a valid fuel material within its range.

*   **Fuel Status Update:** Sets the `is_fueled` variable in the `VariableStorageComponent` to `true`.

### `material_area_checker_failed(pos_x, pos_y)` Function

This function is called when the `MaterialAreaCheckerComponent` no longer detects a valid fuel material.

*   **Fuel Status Update:** Sets the `is_fueled` variable in the `VariableStorageComponent` to `false`.
*   **Laser Deactivation:** Calls `set_lasers(false)` to immediately turn off the lasers when fuel is gone.

## Key Attributes and Variables

*   **`is_fueled` (VariableStorageComponent):** A boolean variable that tracks whether a fuel source is currently present.
*   **`drill_laser` (Entity Tag):** Applied to child entities that contain the actual `LaserEmitterComponent`.
*   **`laser_fx` (Entity Tag):** Applied to components responsible for the visual effects of the lasers.
*   **`igniter` (Entity Tag):** Applied to components related to the fuel igniter, likely for visual feedback.
*   **`LaserEmitterComponent`:** The core component responsible for emitting laser beams.
*   **`MaterialAreaCheckerComponent`:** Detects the presence of specific materials within an area.
*   **`VariableStorageComponent`:** Used to store and retrieve custom variables like `is_fueled`.