---
title: Huussi Interaction Logic
category: scripts
---

# Huussi Interaction Logic

This script defines the behavior when a player interacts with a "Huussi" (toilet) entity in Noita. It primarily handles the unlocking of a "piss" card and the spawning of gold nuggets under specific conditions.

## Core Functionality

The main function `material_area_checker_failed` is triggered by player interaction.

### Interaction Conditions and Outcomes

The script checks for two primary conditions:

1.  **`HasFlagPersistent("card_unlocked_piss")`**: This persistent flag indicates whether the "piss" card has already been unlocked.
2.  **`has_kakken`**: This boolean checks for the presence of an entity with the tag "poopstone" within a 200-unit radius of the interaction point.

The logic branches as follows:

*   **If `card_unlocked_piss` is TRUE and `has_kakken` is FALSE:**
    *   The player has already unlocked the card, and there's no "poopstone" nearby.
    *   The game triggers a random seed based on the interaction position.
    *   There's a 1 in 3 chance (`Random(0, 2) == 1`) to spawn a `goldnugget_200.xml`.
    *   Otherwise, a random number of gold nuggets (`count` between 5 and 19) of type `goldnugget_10.xml` are spawned.

*   **If `card_unlocked_piss` is FALSE or `has_kakken` is TRUE:**
    *   The "piss" card has not been unlocked, or there is "poopstone" present.
    *   An action entity `TOUCH_PISS` is created at the interaction point.
    *   The persistent flag `card_unlocked_piss` is set to TRUE, effectively unlocking the card.

### Audio and Music Cues

Regardless of the outcome, the script also handles audio cues:

*   **`GameTriggerMusicFadeOutAndDequeueAll( 10.0 )`**: Fades out all currently playing music over 10 seconds.
*   **`GameTriggerMusicEvent( "music/oneshot/huussi", false, x, y )`**: Triggers a specific one-shot music event named "huussi" at the interaction coordinates.

## Key Entities and Tags

*   **`poopstone`**: A tag used to identify entities that, when present, alter the interaction outcome.
*   **`goldnugget_200.xml`**: An entity representing a large gold nugget.
*   **`goldnugget_10.xml`**: An entity representing a smaller gold nugget.
*   **`TOUCH_PISS`**: An action entity created to signify the interaction.

## Persistent Flags

*   **`card_unlocked_piss`**: A boolean flag that persists across game sessions, indicating whether the "piss" card has been unlocked.