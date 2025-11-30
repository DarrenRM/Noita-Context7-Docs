---
title: Electricity Perk
category: entities/misc/perks
---

# Electricity Perk

This entity defines the "Electricity" perk in Noita, which grants the player an electrical aura.

## Key Components

### `ElectricitySourceComponent`

This component is responsible for the perk's electrical effects.

*   **`radius`**: The radius (in pixels) around the player that the electrical effect will emanate from.
*   **`emission_interval_frames`**: The number of game frames between each electrical discharge. A lower value means more frequent discharges.

```xml
<ElectricitySourceComponent
    radius="24"
    emission_interval_frames="32"
    >
</ElectricitySourceComponent>
```