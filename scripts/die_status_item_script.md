---
title: Die Status Item Script
category: scripts
---

# Die Status Item Script

This script defines the behavior for a "Die" item in Noita, which triggers various effects based on a random roll. It utilizes a "rolling" status variable to track progress towards a roll and then executes different projectile spawns and animations.

## Key Components

### `bullet_circle` Function

This helper function is responsible for spawning projectiles in a circular pattern around the entity.

*   **`which`**: The name of the projectile to spawn (e.g., "ice", "lightning").
*   **`count`**: The number of projectiles to spawn. Defaults to 4.
*   **`speed`**: The speed of the spawned projectiles. Defaults to 200.
*   **`animal_`**: A boolean flag. If true, spawned projectiles will have a `no_gold_drop` tag.

### Status Tracking

The script uses a `VariableStorageComponent` with the name "rolling" to track the item's status.

*   **`status`**: An integer variable that increments each frame the item is active.
*   **`rstorage`**: Stores the ID of the `VariableStorageComponent` for updating.

### Roll Triggering

When the `status` variable reaches a threshold (20 in this case), a random roll is initiated.

*   **`status >= 20`**: Condition to trigger a roll.
*   **`status = 0`**: Resets the status after a roll.
*   **`Random(1, 6)`**: Determines the primary outcome of the roll (1-6).
*   **`Random(1, 100)`**: Determines a special outcome (less than 100 for standard rolls, otherwise special).

### Roll Outcomes

The script defines different outcomes based on the random rolls:

#### Standard Rolls (Special < 100)

*   **`textprint = "$item_die_" .. tostring(result)`**: Sets the in-game text to display the roll result.
*   **`anim = "rolled_" .. tostring(result)`**: Sets the animation for the item.
*   **Projectile Spawns based on `result`**:
    *   **1**: Spawns 32 "ice" projectiles with speed 500.
    *   **2**: Spawns 12 "lightning" projectiles with speed 2000.
    *   **3**: Spawns 8 "fireball" projectiles with speed 200.
    *   **4**: Spawns 24 "laser\_lasergun" projectiles with speed 900.
    *   **5**: Spawns 8 "fungus" projectiles with speed 300.
    *   **6**: Spawns 10 "tentacle" projectiles with speed 600.

#### Special Rolls (Special >= 100)

*   **`result <= 3` (Bad Roll)**:
    *   **`textprint = textprint .. "bad"`**: Displays "bad" in-game.
    *   **`anim = "rolled_bad"`**: Sets the "bad" animation.
    *   Spawns "circle\_acid\_die.xml" projectile.
*   **`result > 3` (Good Roll)**:
    *   **`textprint = textprint .. "good"`**: Displays "good" in-game.
    *   **`anim = "rolled_good"`**: Sets the "good" animation.
    *   Spawns "deck/regeneration\_field\_long.xml" projectile.

### Visual Updates

*   **`edit_component2( entity_id, "SpriteComponent", ...)`**: Updates the `rect_animation` property of the `SpriteComponent` to reflect the outcome of the roll.
*   **`GamePrint( textprint )`**: Displays the outcome text to the player if players are nearby.