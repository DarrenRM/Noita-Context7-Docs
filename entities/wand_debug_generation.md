---
title: Wand Debug Generation
category: entities
---

# Wand Debug Generation

This file contains functions for debugging and procedurally generating wands in Noita. It's primarily used for testing and creating wands with specific properties.

## Core Functions

### `DEBUG_GetRandomCard()`

This function retrieves a random action ID from the available `actions` table.

### `DEBUG_wand_add_random_cards(gun, entity_id, level)`

This function adds random cards to a wand. It has a chance to add a "rare" card (which can be a modifier, draw many, static projectile, or regular projectile) before filling the remaining deck capacity with randomly selected cards from `DEBUG_GetRandomCard()`.

**Key Parameters:**

*   `gun`: The wand data table.
*   `entity_id`: The ID of the wand entity.
*   `level`: The current level, influencing card generation.

### `DEBUG_generate_gun(cost, level, force_unshuffle)`

This is the main function for generating a debug wand. It sets a random seed based on the wand's position, retrieves gun data using `get_gun_data`, creates the wand from this data, and then populates it with random cards.

**Key Parameters:**

*   `cost`: The cost of the generated wand.
*   `level`: The level of the generated wand.
*   `force_unshuffle`: A boolean to force the wand to be unshuffled.

## Example Usage

The file concludes with an example call to `DEBUG_generate_gun`:

```lua
DEBUG_generate_gun( 180, 11, false )
```

This would generate a debug wand with a cost of 180, at level 11, and without forcing it to be unshuffled.