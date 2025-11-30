---
title: Shock Powder Entity
category: entities
---

# Shock Powder Entity

This document describes the `shock_powder.xml` entity, which represents a consumable item that emits electrical charges.

## Key Components

### ElectricityComponent

This component governs the electrical properties of the entity.

*   **`probability_to_heat`**: (float) The probability that this entity will generate heat when it discharges electricity.

### ElectricChargeComponent

This component manages the emission of electrical charges.

*   **`charge_time_frames`**: (int) The number of frames required to fully charge the entity before it can discharge.
*   **`electricity_emission_interval_frames`**: (int) The interval in frames between successive electrical discharges.

### LifetimeComponent

This component defines how long the entity persists in the game world.

*   **`lifetime`**: (float) The total duration in seconds the entity will exist before despawning.