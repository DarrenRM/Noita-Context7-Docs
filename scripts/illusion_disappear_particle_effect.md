---
title: Illusion Disappear Particle Effect
category: scripts
---

# Illusion Disappear Particle Effect

This script is responsible for spawning a visual particle effect when an entity disappears, simulating an illusionary vanishing.

## Core Functionality

The primary purpose of this script is to trigger a visual cue for entity disappearance.

### Key Attributes

*   **`entity_id`**: Retrieves the unique identifier of the entity that is disappearing.
*   **`pos_x`, `pos_y`**: Gets the current X and Y coordinates of the disappearing entity.
*   **`EntityLoad("data/entities/particles/poof_blue.xml", pos_x, pos_y)`**: This is the core function call. It loads and spawns the `poof_blue.xml` particle effect at the entity's location.

## Usage

This script is typically called by other game systems when an entity is intended to disappear in an illusory manner. It does not contain complex logic or configurable parameters beyond the particle effect it spawns.

## Dependencies

*   `data/scripts/lib/utilities.lua`: This file is included for potential utility functions, though in this specific script, it's not directly utilized for its core functionality.
*   `data/entities/particles/poof_blue.xml`: This XML file defines the visual appearance and behavior of the particle effect itself.