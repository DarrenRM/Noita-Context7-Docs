---
title: Failed Alchemist Aura
category: scripts
---

# Failed Alchemist Aura

This script implements a passive aura effect for a "Failed Alchemist" entity. When activated, it scans for nearby enemies and applies a "protection_all_short_evil" effect to them, provided they don't already possess a similar protection.

## Key Functionality

*   **Radius Scan:** Detects entities with the "enemy" tag within a radius of 128 pixels.
*   **Protection Check:** Iterates through children of detected enemies to see if they already have a "protection_all_short" component.
*   **Effect Application:** If an enemy does not have the specified protection, it loads and applies the `effect_protection_all_short_evil.xml` entity to it.

## Core Logic

The script primarily focuses on the following steps:

1.  **Get Entity Information:** Retrieves the current entity's ID and its world coordinates.
2.  **Identify Targets:** Uses `EntityGetInRadiusWithTag` to find all entities tagged as "enemy" within the defined radius.
3.  **Iterate and Validate:** For each detected enemy:
    *   It checks if the enemy is not the source of the aura itself.
    *   It examines the enemy's children for any components related to protection.
    *   If no "protection\_all\_short" component is found on any child, the enemy is considered "valid" for the effect.
4.  **Apply Effect:** For valid enemies, it loads a pre-defined effect entity (`effect_protection_all_short_evil.xml`) at the enemy's location and attaches it as a child to the enemy.

## Key Attributes/Elements

*   `entity_id`: The unique identifier of the entity executing this script.
*   `x`, `y`: The world coordinates of the entity.
*   `r`: The radius (128 pixels) for detecting nearby enemies.
*   `"enemy"`: The tag used to identify target entities.
*   `EntityGetAllChildren()`: Function to retrieve all child entities of a given entity.
*   `EntityGetComponent()`: Function to retrieve specific components from an entity.
*   `"GameEffectComponent", "protection_all_short"`: The specific component and its type being checked for.
*   `valid`: A boolean flag indicating whether the target enemy is eligible for the effect.
*   `EntityLoad()`: Function to load an entity from an XML file.
*   `"data/entities/misc/effect_protection_all_short_evil.xml"`: The path to the XML file defining the protection effect.
*   `EntityAddChild()`: Function to attach one entity as a child to another.