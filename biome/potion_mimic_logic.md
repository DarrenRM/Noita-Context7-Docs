---
title: Potion Mimic Logic
category: biome
---

# Potion Mimic Logic

This document describes the AI-assisted modding information for the Potion Mimic logic in Noita.

## Lua Component

The core logic for potion mimics is handled by a Lua script.

### `puzzle_logic_potion_mimics.lua`

This script defines the behavior and interactions of potion mimics within the game world.

#### Key Attributes:

*   **`script_source_file`**: Specifies the path to the Lua script responsible for the mimic's logic.
*   **`execute_every_n_frame`**: Controls how frequently the script's logic is executed, impacting performance and responsiveness. A value of `30` means the script runs every 30 frames.

---
SKIP