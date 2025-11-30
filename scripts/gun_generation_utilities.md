---
title: Gun Generation Utilities
category: scripts
---

# Gun Generation Utilities

This script provides utility functions for procedurally generating guns in Noita, focusing on modifying their properties and appearance.

## Core Functions

### `D(size)` and `D10()`

These functions are simple dice roll simulations.

*   `D(size)`: Returns a random integer between 1 and `size` (inclusive).
*   `D10()`: A convenience function that returns a random integer between 1 and 10.

### `AddGunAction(entity_id, action_id)`

Attaches a specific action (spell) to a gun entity.

*   `entity_id`: The ID of the gun entity to modify.
*   `action_id`: The ID of the action entity to add.

### `SetItemSprite(entity_id, ability_comp, item_file, r)`

Sets the sprite for a gun item, handling variations based on a random number.

*   `entity_id`: The ID of the gun entity.
*   `ability_comp`: The `AbilityComponent` of the gun.
*   `item_file`: The base filename for the sprite.
*   `r`: A random number used to select a specific sprite variation (e.g., for different damage levels or types).

### `gun_gen(gun, entity_id)`

The primary function for generating and configuring a gun. It takes a `gun` table (defining desired properties) and an `entity_id` and applies these properties to the entity.

#### Key Gun Properties Modified:

*   **`ui_name`**: The display name of the gun. Can be prefixed with a random adjective from `gun_names`.
*   **`deck_capacity`**: The maximum number of spells the gun can hold.
*   **`actions_per_round`**: The number of spells cast per firing cycle.
*   **`reload_time`**: The time it takes for the gun to reload.
*   **`shuffle_deck_when_empty`**: Whether the spell deck is shuffled when depleted.
*   **`fire_rate_wait`**: The delay between shots.
*   **`spread_degrees`**: The angular spread of projectiles.
*   **`speed_multiplier`**: Multiplier for projectile speed.
*   **`rare_chance`**: Chance for the gun to become a "rare" variant.
*   **`rare_type`**: The type of rare variant.
*   **Light Component**: Modifies the color and intensity of the gun's light.

#### `gun` Table Structure (Example):

```lua
local my_gun_config = {
    capacity = 10,
    actions_per_round = 2,
    reload = 0.5,
    shuffle = true,
    rare_chance = 0.1, -- 10% chance
    rare_type = "elemental",
    firerate = 0.1,
    spread = 5,
    bullet_speed = 1.5,
    actions = {
        "data/actions/fireball.xml",
        "data/actions/magic_missile.xml",
    },
    light_r = 255,
    light_g = 100,
    light_b = 0,
}
```

### `convert_to_int(value)`

Converts a boolean value to an integer (1 for true, 0 for false). This is often used for properties that expect integer representations of boolean states.

## `gun_names` Table

A large table of adjectives used to procedurally generate unique gun names.

```lua
gun_names = {
  'Deadly','Rusty','Old','New','Shiny','Lethal','Dangerous','Large','Enormous','Tiny','Small','Big','Pretty','Terrifying','Confusing',
  'Mystery','Superior','Inferior','Destructive','Chaotic','Lawful','Good','Bad','Neutral','Worn','Polished','Waxen','Strong','Weak',
  'Complex','Tactical','Horrifying','Scary','Scratched','Untested','Prototype','Type a','Type b','Type x','Secret','Special','Unique',
  'Mega','Super','Giga','Turbo','Hyper','Alpha','Omega','Extreme','Vanilla','Flavourful','Sturdy','Solid','Used','Unused','Grey','Gray',
  'Sepia','Secretly','Actual','Genuine','Powerful','Double','Triple','Stereo','Ancient','Antique','Rustic','Artisan','Slick','Slim',
  'Bulky','Heavy','Efficient','Fast','Quick','Rapid','Slow','Veteran','Agile','Bitcoin','Online',
}
```