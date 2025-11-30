---
title: Creature Genome Relations
category: data
---

---

# Creature Genome Relations

This document details the genetic compatibility and aggression levels between various creatures in Noita, as defined in `genome_relations.csv`. This data is crucial for understanding how different entities will interact with each other and the player.

## Understanding the Data

The `genome_relations.csv` file is structured as a matrix. Each row and column represents a creature type. The value at the intersection of a row and column indicates the relationship score between those two creatures.

*   **Row Creature:** The creature type initiating the interaction or being considered from the perspective of the row.
*   **Column Creature:** The creature type being interacted with or observed from the perspective of the column.
*   **Relationship Score:** A numerical value representing the interaction. Higher values generally indicate greater aggression or compatibility, while lower values indicate neutrality or avoidance.

## Key Attributes and Interactions

The following table summarizes some of the most significant relationships. Scores range from 0 (no interaction/passive) to 100 (highly aggressive/compatible).

| Row Creature   | Player | Slimes | Ants   | Robots | Flies  | Orcs   | Spiders | Zombies | Mages  | Nests  |
| :------------- | :----- | :----- | :----- | :----- | :----- | :----- | :------ | :------ | :----- | :----- |
| **Player**     | 100    | 0      | 0      | 0      | 0      | 2      | 0       | 0       | 0      | 0      |
| **Slimes**     | 0      | 100    | 80     | 95     | 90     | 80     | 95      | 90      | 90     | 100    |
| **Ants**       | 0      | 80     | 100    | 40     | 90     | 50     | 40      | 0       | 0      | 100    |
| **Robots**     | 0      | 95     | 90     | 100    | 80     | 95     | 95      | 90      | 90     | 100    |
| **Flies**      | 0      | 90     | 90     | 90     | 100    | 60     | 90      | 90      | 90     | 100    |
| **Orcs**       | 2      | 80     | 80     | 95     | 90     | 0      | 100     | 0       | 0      | 0      |
| **Spiders**    | 0      | 95     | 95     | 95     | 90     | 95     | 100     | 95      | 95     | 100    |
| **Zombies**    | 0      | 90     | 0      | 90     | 90     | 0      | 95      | 100     | 90     | 100    |
| **Mages**      | 0      | 90     | 0      | 90     | 90     | 0      | 95      | 90      | 100    | 100    |
| **Nests**      | 0      | 100    | 100    | 100    | 100    | 0      | 100     | 100     | 100    | 100    |

**Summary of Notable Interactions:**

*   **Player:** Most creatures are neutral or aggressive towards the player (score of 0 or higher). Only "target" has a direct positive score with the player, indicating a specific interaction.
*   **Nests:** Nests are highly compatible with most creatures, especially other aggressive types like slimes, robots, and spiders.
*   **Aggression:** Creatures like spiders, slimes, and robots exhibit high aggression towards many other types.
*   **Player vs. Orcs:** Orcs have a very low score (2) with the player, suggesting a specific, less aggressive interaction compared to other hostile mobs.
*   **Specific Compatibilities:**
    *   Slimes and Ants have a strong relationship (80).
    *   Robots and Flies have a moderate relationship (80).
    *   Spiders and Slimes have a high relationship (95).

## Creature Categories and Their General Behavior

The data can be broadly categorized by creature type, revealing general behavioral tendencies:

### Hostile Creatures

These creatures generally have high aggression scores towards the player and often towards each other.

*   **Slimes, Spiders, Robots, Flies:** Exhibit high aggression across the board.
*   **Orcs, Zombies, Mages:** Also highly aggressive, with some specific variations in their interactions.
*   **Worms, Bats:** Tend to be aggressive.

### Neutral/Passive Creatures

These creatures may have lower aggression scores or specific interactions.

*   **Player:** The baseline for interactions.
*   **Helpless, Eels:** Appear to be more passive or have limited aggressive interactions.

### Special Cases

*   **Nests:** Act as hubs, showing high compatibility with many aggressive creatures, suggesting they spawn or attract them.
*   **Traps:** Have varied interactions, some aggressive, some less so.
*   **Curse:** Shows high compatibility with many entities, potentially indicating its effect on them.
*   **Target:** Specifically interacts with the player.

## Modding Implications

Understanding these genome relations is vital for AI modding:

*   **AI Behavior:** Directly influences how creatures perceive and react to each other and the player.
*   **Encounter Design:** Allows for the creation of specific combat scenarios and creature groupings.
*   **New Creature Creation:** When introducing new creatures, their genome relations will define their place in the ecosystem and their threat level.
*   **Balance Adjustments:** Modifying these scores can significantly alter game difficulty and creature dynamics.

By adjusting these values, modders can create unique and challenging gameplay experiences, altering the fundamental interactions within the Noita world.