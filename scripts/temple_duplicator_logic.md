---
title: Temple Duplicator Logic
category: scripts
---

# Temple Duplicator Logic

This script defines the behavior of the Temple Duplicator entity in Noita, which duplicates a nearby "card action" entity and adds shop-related components to it.

## Core Functionality

The `collision_trigger` function is the primary logic for the duplicator. It's designed to be called when the duplicator collides with another entity.

### Key Steps:

1.  **Identify Duplicator:** Gets the unique ID of the duplicator entity itself.
2.  **Find Closest Card Action:** Searches for the nearest entity with the tag "card\_action" at the duplicator's position.
3.  **Extract Action ID:** Retrieves the `action_id` from the found "card action" entity's `ItemActionComponent`. This ID identifies the specific spell or action to be duplicated.
4.  **Create Duplicated Entity:** If a valid `action_id` is found, it creates a new item action entity using `CreateItemActionEntity`.
5.  **Calculate Cost:** Determines the cost of the duplicated card. It iterates through the `actions` table to find the original card's price and applies a 20% markup.
6.  **Add Shop Components:**
    *   **SpriteComponent (for cost display):** Adds a sprite to display the calculated cost.
    *   **ItemCostComponent:** Assigns the calculated cost to the duplicated entity.
    *   **LuaComponent:** Attaches a `shop_effect.lua` script to handle what happens when the duplicated item is picked up.
7.  **Display Uses Remaining (if applicable):** If the original card has a limited number of uses (`uses_remaining` > -1), it adds another `SpriteComponent` to display this count on the duplicated entity.
8.  **Destroy Duplicator:** The original duplicator entity is then destroyed.

## Key Attributes & Components

### `collision_trigger()` Function

*   **Purpose:** Handles the duplication logic upon collision.
*   **Key Actions:**
    *   Finds the closest entity with the `card_action` tag.
    *   Extracts the `action_id` from the target entity.
    *   Creates a new item action entity based on the `action_id`.
    *   Calculates and applies shop cost components.
    *   Attaches a pickup script (`shop_effect.lua`).
    *   Displays remaining uses if applicable.
    *   Destroys the duplicator.

### `CreateItemActionEntity( action_id, x, y )`

*   **Purpose:** A utility function (likely from `gun_actions.lua`) that creates a new entity representing an item action, using the provided `action_id` and world coordinates.

### `ItemActionComponent`

*   **Purpose:** Attached to entities that represent actions or spells that can be picked up.
*   **Key Attribute:** `action_id` - A string identifier for the specific action.

### `ItemCostComponent`

*   **Purpose:** Defines the cost of an item in a shop context.
*   **Key Attribute:** `cost` - The numerical cost of the item.

### `SpriteComponent` (for text display)

*   **Purpose:** Used to render text on entities, primarily for displaying costs and uses remaining.
*   **Key Attributes:**
    *   `image_file`: Typically points to a font texture (e.g., `data/fonts/font_pixel_white.xml`).
    *   `is_text_sprite`: Set to `1` to indicate it's a text sprite.
    *   `text`: The string content to display.
    *   `offset_x`, `offset_y`: Position relative to the entity's transform.
    *   `has_special_scale`, `special_scale_x`, `special_scale_y`: For scaling text.

### `LuaComponent` (for pickup logic)

*   **Purpose:** Allows attaching Lua scripts to entities that execute at specific times.
*   **Key Attribute:** `script_item_picked_up` - Specifies the Lua script to run when the item is picked up by the player.

### `actions` Table (External Reference)

*   **Purpose:** This script references an external `actions` table (likely defined elsewhere, e.g., in `data/scripts/gun/actions.lua`).
*   **Key Attribute Used:** `price` - Used to determine the base cost for duplication.

---