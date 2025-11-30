---
title: Wizard Returner Memory Script
category: scripts
---

# Wizard Returner Memory Script

This script defines the behavior for the "Wizard Returner" entity, specifically how it "remembers" and reuses projectiles.

## Core Functionality

The primary purpose of this script is to allow the Wizard Returner to mimic the last projectile it was hit by.

### Key Attributes & Logic

*   **Projectile Acquisition:**
    *   The script scans for nearby entities tagged as "projectile".
    *   It randomly selects one of these projectiles.
    *   It then attempts to retrieve the `projectile_file` name from the selected projectile's `VariableStorageComponent`.
*   **Projectile Mimicry:**
    *   If a `projectile_file` is successfully identified, the script updates the Wizard Returner's `AnimalAIComponent`.
    *   Specifically, it sets the `attack_ranged_entity_file` to the name of the remembered projectile. This means the Wizard Returner will now fire that projectile type.

## Technical Details

*   **Entity Identification:** Uses `GetUpdatedEntityID()` to get the current entity's ID.
*   **Proximity Scan:** Employs `EntityGetInRadiusWithTag()` to find nearby projectiles.
*   **Component Access:** Utilizes `EntityGetComponent()` and `ComponentGetValue2()` to read component data.
*   **Component Modification:** Uses `ComponentSetValue2()` to update the AI component.
*   **Randomization:** `SetRandomSeed()` and `Random()` are used for projectile selection.

## Example Usage (Conceptual)

Imagine a Wizard Returner is hit by a "fireball" projectile. This script will detect the "fireball" projectile, extract its file name, and then configure the Wizard Returner to fire "fireball" projectiles in its subsequent attacks.