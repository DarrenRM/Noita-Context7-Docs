---
title: Player Biome Tracking Script
category: scripts
---

# Player Biome Tracking Script

This script is responsible for tracking the biomes the player visits and updating global game variables accordingly. It primarily focuses on recording visited biomes and tracking progress within the Holy Mountain.

## Core Functionality

The script performs the following key actions:

*   **Determines Current Biome:** It gets the player's current position and uses `BiomeMapGetName` to identify the biome they are in.
*   **Tracks Visited Biomes:** It maintains a comma-separated string of visited biomes in the global variable `visited_biomes`. New biomes are added to the front of this string.
*   **Counts Visited Biomes:** A global variable `visited_biomes_count` keeps track of the total number of unique biomes visited. This count is capped at 1000.
*   **Manages Holy Mountain Progress:** It specifically checks if the player is in the "holymountain" or "victoryroom" biomes.
*   **Records Holy Mountain Depth:** If the player enters a Holy Mountain at a deeper level than previously recorded, it updates the `HOLY_MOUNTAIN_DEPTH` global variable.
*   **Counts Holy Mountain Visits:** It increments the `HOLY_MOUNTAIN_VISITS` global variable each time the player enters a Holy Mountain.

## Key Global Variables Managed

The script interacts with and modifies the following global variables:

| Variable Name             | Description