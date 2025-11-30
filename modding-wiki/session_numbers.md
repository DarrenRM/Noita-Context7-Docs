---
title: Session Numbers
source: https://noita.wiki.gg/wiki/Documentation:SessionNumbers
category: modding-wiki
---

# Session Numbers

This documentation explains the concept of "Session Numbers" in Noita, which are numerical identifiers used internally by the game to track various entities and events during a gameplay session. Understanding these numbers is crucial for modders who need to interact with or manipulate game state, such as identifying specific enemies, projectiles, or effects for custom logic.

## What are Session Numbers?

Session Numbers are dynamic, unique identifiers assigned to game objects and events as they are created or occur within a Noita session. They are not persistent across game restarts and are primarily used by the game's internal systems for efficient referencing and management of game elements.

### Types of Session Numbers

While the wiki page itself is empty, the concept of session numbers generally applies to various game entities. In the context of Noita modding, these might include:

*   **Entity IDs:** Unique numbers assigned to every spawned entity (enemies, items, projectiles, etc.).
*   **Effect IDs:** Identifiers for active status effects or temporary buffs/debuffs.
*   **Event IDs:** Numbers associated with specific game events that can be listened to or triggered by mods.

Modders often need to access or manipulate these session numbers through the Lua API to implement custom behaviors, such as:

*   Targeting specific enemies with custom spells.
*   Modifying the properties of spawned items.
*   Responding to in-game events with unique actions.

**Note:** As the original wiki page for "Documentation:SessionNumbers" is empty, this explanation is based on the general understanding of session numbers in game development and their likely application within Noita's modding context. For specific implementation details and available Lua functions, refer to the [Lua API documentation](https://noita.wiki.gg/wiki/Modding:_Lua_API).