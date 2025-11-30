---
title: Ingest Projectiles Perk
category: scripts/perks
---

# Ingest Projectiles Perk

This perk allows the player to ingest incoming projectiles, converting a portion of their damage into material ingestion.

## Key Attributes

*   **`ingest_chance`**: The base probability of a projectile being ingested. (Default: `0.33`)
*   **`ingestion_damage_scale`**: A multiplier applied to the projectile's damage to determine the amount of material ingested. (Default: `250`)
*   **`max_ingestion`**: The maximum amount of material that can be ingested from a single projectile. (Default: `150`)

## Functionality

The `damage_about_to_be_received` function is triggered when the player is about to take damage.

1.  It calculates the amount of material to ingest based on the incoming damage, the `ingestion_damage_scale`, and capped by `max_ingestion`.
2.  It then uses `EntityIngestMaterial` to ingest "water" (represented by `CellFactory_GetType("water")`) into the player's entity.
3.  The incoming damage is effectively nullified (`damage*0.0`), and the critical chance is halved (`critical_chance*0.5`).

## Notes

*   The commented-out section suggests that the ingestion might have been intended to only apply to projectile damage and be influenced by a procedural chance based on position.
*   There is a `TODO` comment indicating that audio for ingestion is missing.