---
title: Plague Rats Death Perk
category: scripts/perks
---

# Plague Rats Death Perk

This script defines the behavior for the "Plague Rats" perk when the player dies. It focuses on spawning additional plague rats.

## Core Functionality

The `death` function is triggered when the player entity is destroyed. Its primary role is to conditionally spawn more "plague rats" based on the number of times the perk has been picked up.

### Key Attributes and Logic

*   **`flag_name = "RAT_PERK_TOTAL_COUNT"`**: A global flag used to track the total number of times the Plague Rats perk has been acquired by the player.
*   **`pickup_count = tonumber( GlobalsGetValue( flag_name, "0" ) )`**: Retrieves the current value of the `RAT_PERK_TOTAL_COUNT` flag, defaulting to "0" if it doesn't exist.
*   **`rat_count = math.min( 1 + pickup_count, 10 )`**: Determines the number of rats to potentially spawn. This is calculated as 1 plus the `pickup_count`, capped at a maximum of 10 rats.
*   **`rats = EntityGetWithTag( "plague_rats" )`**: Gets a list of all entities currently tagged as "plague\_rats".
*   **`if ( #rats < 30 ) then ... end`**: A condition to prevent excessive spawning. Rats will only be spawned if the current number of plague rats on screen is less than 30.
*   **`for i=1,rat_count do ... end`**: Loops to potentially spawn rats, up to the calculated `rat_count`.
*   **`if ( rnd > 50 ) then ... end`**: A 50% chance for each iteration of the loop to actually spawn a rat.
*   **`EntityLoad( "data/entities/misc/perks/plague_rats_rat.xml", pos_x, pos_y )`**: Loads the "plague\_rats\_rat.xml" entity at the player's death position.

### Summary of Logic

1.  When the player dies, the `death` function is called.
2.  It checks a global counter for how many times the Plague Rats perk has been picked up.
3.  It calculates a target number of rats to spawn, increasing with perk pickups but capped at 10.
4.  It checks if there are already many plague rats present (less than 30).
5.  If the conditions are met, it attempts to spawn rats, with a 50% chance per rat in the target count.
6.  The spawned rats are loaded from `data/entities/misc/perks/plague_rats_rat.xml`.