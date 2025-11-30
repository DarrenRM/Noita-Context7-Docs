---
title: Loose Collapsed Temple Chunks
category: entities
---

# Loose Collapsed Temple Chunks

This entity defines loose chunks of collapsed temple material that can appear in the game. These are primarily used to facilitate player movement through collapsed temple areas, especially when players loop back into such areas via portals.

## Key Components

### LooseGroundComponent

This component governs the behavior of the loose ground chunks.

| Attribute          | Description                                                                                             |
| :----------------- | :------------------------------------------------------------------------------------------------------ |
| `probability`      | The base probability of these chunks appearing. (0.25)                                                  |
| `max_distance`     | The maximum distance from the player at which these chunks can spawn. (180)                             |
| `max_angle`        | The maximum angle relative to the player's direction for spawning. (2.1 radians)                        |
| `chunk_probability`| The probability of a specific chunk forming. (0.15)                                                     |
| `collapse_images`  | A path pattern for the images used for the collapsing effect. (`data/procedural_gfx/collapse_big/$[0-14].png`) |
| `chunk_material`   | The material type of the generated chunks. (`concrete_collapsed`)                                     |

### LifetimeComponent

This component defines how long the loose chunks persist.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `lifetime`            | The base duration the chunks will exist. (320 frames)                    |
| `randomize_lifetime`  | A range to randomize the lifetime, adding variation. (`min="-50"`, `max="50"`) |