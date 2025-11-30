---
title: Common Development Translations
category: data/translations/
---

# Common Development Translations

This file contains common text strings used in Noita's development and potentially for modding. It primarily serves as a localization file for various languages.

## Key Attributes

*   **`en`**: English translation.
*   **`ru`**: Russian translation.
*   **`pt-br`**: Brazilian Portuguese translation.
*   **`es-es`**: Spanish (Spain) translation.
*   **`de`**: German translation.
*   **`fr-fr`**: French (France) translation.
*   **`it`**: Italian translation.
*   **`pl`**: Polish translation.
*   **`zh-cn`**: Simplified Chinese translation.
*   **`jp`**: Japanese translation.
*   **`ko`**: Korean translation.
*   **`NOTES`**: A field for developer notes, often using `\n` for newlines.
*   **`max length`**: Specifies the maximum allowed length for the translated string.

## Usage for AI-Assisted Modding

This file is crucial for ensuring your mods are accessible to a wider audience by providing translations. When developing mods that introduce new text (e.g., item descriptions, spell names, UI elements), you would typically:

1.  **Identify New Text:** Determine all the new text strings your mod introduces.
2.  **Add to Translation Files:** Add these new strings to the appropriate translation files. For common UI or game-wide elements, `common_dev.csv` might be a starting point, or you might create a dedicated file for your mod.
3.  **Provide Translations:** For each new string, provide translations for the languages you wish to support. AI translation tools can be leveraged here, but manual review is highly recommended for accuracy and cultural appropriateness.
4.  **Reference in Mod:** Ensure your mod's configuration files (e.g., `.xml` or `.lua`) correctly reference these translation keys.

**Example of a potential entry (hypothetical):**

| Key        | en                 | ru                 | pt-br              | ... | NOTES                               | max length |
| :--------- | :----------------- | :----------------- | :----------------- | :-- | :---------------------------------- | :--------- |
| `my_mod_item_name` | My Awesome Wand    | Мой Потрясающий Жезл | Meu Bastão Incrível | ... | Name of the new powerful wand.      | 50         |
| `my_mod_item_desc` | A wand of great power. | Жезл великой силы. | Um bastão de grande poder. | ... | Description for the awesome wand. | 150        |

This file acts as a central hub for localized text, making it easier to manage and update translations for your Noita mods.