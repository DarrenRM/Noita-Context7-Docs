---
title: Boss Centipede Spawn Rewards Logic
category: entities
---

# Boss Centipede Spawn Rewards Logic

This script defines the logic for determining and spawning rewards after defeating the Boss Centipede. It analyzes various player statistics from the current run to decide which reward entities to instantiate.

## Key Player Statistics Analyzed

The script retrieves the following player statistics to influence reward generation:

*   **`enemies_killed`**: Total number of enemies defeated in the current run.
*   **`playtime`**: Total time played in the current run (in seconds).
*   **`projectiles_shot`**: Number of projectiles fired.
*   **`gold`**: Current amount of gold the player possesses.
*   **`gold_all`**: Total gold accumulated throughout the run (including spent).
*   **`orbs`**: Total number of orbs collected in the current run.
*   **`damage_taken`**: Total damage taken by the player.
*   **`wands_edited`**: Number of times wands have been tinkered with.
*   **`kicks`**: Number of times the player has kicked.
*   **`boss_kill_count`**: Total number of bosses killed in the current run.
*   **`biomes_visited_with_wands`**: Number of biomes visited while possessing wands.

## Reward Conditions and Spawns

The script checks for specific conditions based on the player statistics and spawns corresponding reward entities. Multiple rewards can be spawned if multiple conditions are met.

### Pacifist and Near-Pacifist Rewards

*   **Pacifist (`enemies_killed <= 0`)**: Spawns `reward_peace.xml`. Also sets a persistent flag `progress_pacifist`.
*   **Almost Pacifist (`enemies_killed <= boss_kill_count`)**: Spawns `reward_almostpacifist.xml`.

### Combat Style Rewards

*   **Kicks Only (`projectiles_shot <= 0 and kicks > 0`)**: Spawns `reward_kicksonly.xml`.
*   **No Hit (`damage_taken <= 0`)**: Spawns `reward_nohit.xml`. Also sets a persistent flag `progress_nohit`.

### Wand Usage Rewards

*   **No Wands (`biomes_with_wands <= 0`)**: Spawns `reward_nowands.xml`.
*   **No Wand Tinkering (`wands_edited <= 0`)**: Spawns `reward_notinkeringofwands.xml`.

### Time-Based Rewards

*   **Speedrun (<= 60 seconds)**: Spawns `reward_minit.xml`. Also sets a persistent flag `progress_minit`.
*   **Fast Run (<= 5 minutes)**: Spawns `reward_clock.xml`. Also sets a persistent flag `progress_clock`.

### Orb Collection Reward

*   **Max Orbs (`orbs >= MAX_ORB_COUNT`)**: Spawns `reward_crown.xml`.

### Gold-Based Rewards

*   **No Gold Collected (`money_all_time <= 0`)**: Spawns `reward_nolla.xml`. Also sets a persistent flag `progress_nogold`.
*   **Millionaire (`money_now >= 1000000`)**: Spawns `giant_dollar.xml`.
*   **Half Millionaire (`money_now >= 500000`)**: Spawns `reward_dollar.xml`.

### Default Reward

*   **No Specific Rewards Met (`spawned_n <= 0`)**: If no other rewards are triggered, spawns `gold_reward.xml`.

### Sun Reward

*   **Sun Kill (`GameHasFlagRun("sun_kill")`)**: Spawns `reward_sun.xml`. Also sets a persistent flag `progress_sunkill`.

## Reward Entity Loading

Reward entities are loaded using `EntityLoad(filepath, x, y)`. The `x` and `y` coordinates are adjusted slightly for each spawned reward to prevent overlap.

```lua
-- Example of spawning a reward
entity = EntityLoad( "data/entities/animals/boss_centipede/rewards/reward_peace.xml", x + spawned_n * 20, y - spawned_n * 10)
spawned_n = spawned_n + 1
```