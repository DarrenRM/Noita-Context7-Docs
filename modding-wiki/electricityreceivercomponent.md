---
title: ElectricityReceiverComponent
source: https://noita.wiki.gg/wiki/Documentation:ElectricityReceiverComponent
category: modding-wiki
---

# ElectricityReceiverComponent

This documentation page details the `ElectricityReceiverComponent` in Noita, a crucial component for creating entities that can receive and react to electrical power. Understanding this component is essential for modders looking to implement interactive objects, power systems, or unique electrical effects within their mods.

## Overview

The `ElectricityReceiverComponent` allows entities to act as receivers for electrical signals. When an entity with this component is connected to a power source (like a battery or a generator), it can trigger various effects or behaviors based on the received electricity. This is fundamental for building complex contraptions and interactive elements in Noita mods.

## Component Properties

The `ElectricityReceiverComponent` has several properties that can be configured in an entity's XML definition to control its behavior.

### `receive_power_amount`

*   **Type:** float
*   **Description:** The amount of electrical power this receiver consumes or reacts to. This value determines how much "charge" is needed to trigger its effects.

### `power_consumption_type`

*   **Type:** enum
*   **Description:** Defines how the power consumption is measured.

    | Value        | Description