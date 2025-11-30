---
title: Orb Initialization Script
category: scripts
---

---

# Orb Initialization Script

This script handles the initialization of Orbs in Noita, specifically modifying their appearance and behavior based on their `orb_id`.

## Key Functionality

The primary purpose of this script is to:

*   **Identify Orbs:** It retrieves the `OrbComponent` to determine the unique `orb_id` of the orb.
*   **Conditional Modification:** If the `orb_id` is 100 or greater, it triggers specific modifications.
*   **Reset Card Name:** For orbs with `orb_id >= 100`, it resets the `card_name` stored in a `VariableStorageComponent` to an empty string. This likely prevents unintended card associations.
*   **Change Sprite:** For orbs with `orb_id >= 100`, it changes the orb's sprite to `data/items_gfx/orbs/orb_red_evil.xml`, giving it a distinct visual appearance.

## Core Components and Attributes

The script interacts with the following Noita components:

### OrbComponent

*   **Purpose:** Identifies the orb and assigns it a unique ID.
*   **Key Attribute:**
    *   `orb_id`: An integer representing the specific type or variant of the orb.

### VariableStorageComponent

*   **Purpose:** Stores arbitrary variables associated with an entity.
*   **Key Attributes:**
    *   `name`: The name of the variable (e.g., "card_name").
    *   `value_string`: The string value of the variable. This is reset to `""` for `card_name` under specific conditions.

### SpriteComponent

*   **Purpose:** Defines the visual appearance of an entity.
*   **Key Attribute:**
    *   `image_file`: The path to the sprite's XML definition. This is updated to `data/items_gfx/orbs/orb_red_evil.xml` for specific orbs.

## Script Logic Flow

1.  **Get Entity Information:** Retrieves the current entity's ID and position.
2.  **Find Orb ID:** Iterates through `OrbComponent`s to find the `orb_id`.
3.  **Conditional Check:** If `orb_id` is 100 or greater:
    *   **Reset `card_name`:** Locates `VariableStorageComponent`s and sets the `value_string` of any component named "card_name" to an empty string.
    *   **Update Sprite:** Locates `SpriteComponent`s and changes the `image_file` to `data/items_gfx/orbs/orb_red_evil.xml`.