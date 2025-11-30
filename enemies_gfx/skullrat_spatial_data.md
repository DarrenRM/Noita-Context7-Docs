---
title: Skullrat Spatial Data
category: data/enemies_gfx
---

# Skullrat Spatial Data

This document describes the spatial data for the Skullrat enemy in Noita, specifically its key attachment points. This information is crucial for AI-assisted modding, particularly when dealing with animations, hitboxes, or custom effects tied to specific body parts.

## Key Attachment Points

The following table lists the primary attachment points for the Skullrat, along with their associated color codes. These color codes are often used internally by the game engine to identify and manipulate these points.

| Attachment | Color Code | Description |
|---|---|---|
| `left_foot` | `ffff0000` | The left foot of the Skullrat. |
| `right_foot` | `ff800000` | The right foot of the Skullrat. |
| `left_hand` | `ffff00ff` | The left hand of the Skullrat. |
| `right_hand` | `ff0000ff` | The right hand of the Skullrat. |
| `head` | `ffffff00` | The head of the Skullrat. |
| `tail` | `ff00ffff` | The tail of the Skullrat. |
| `center` | `ff00ff00` | The central pivot point of the Skullrat. |

## Usage in Modding

Understanding these spatial data points allows modders to:

*   **Precisely target hitboxes:** Apply damage or effects to specific body parts.
*   **Attach custom sprites or particles:** For example, adding glowing effects to the head or a trailing effect to the tail.
*   **Influence animations:** Ensure animations correctly align with the creature's anatomy.
*   **Create custom AI behaviors:** Trigger actions based on the position of specific body parts.

While this file only lists the attachment points, their corresponding sprite sheets and animation data would be found in other related files within the `enemies_gfx` directory.