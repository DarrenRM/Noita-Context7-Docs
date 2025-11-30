---
title: Noita Modding Guide
source: https://noita.wiki.gg/wiki/Modding
category: modding-wiki
---

# Noita Modding Guide

This documentation provides a comprehensive overview of modding Noita, covering essential tools, fundamental concepts, and practical steps for getting started. Understanding these elements is crucial for anyone looking to create or modify game content, from simple tweaks to complex new features.

## Introduction to Modding Noita

Noita's modding capabilities are primarily driven by **Lua scripting** and **XML configuration**, operating within an **Entity Component System (ECS)** framework. This means that most in-game elements—enemies, projectiles, wands, and even the player—are treated as entities composed of various components. While a strong grasp of Lua is beneficial, significant modifications can be achieved by editing XML files and spritesheets without extensive programming knowledge.

### Essential Tools for Modding

To begin your modding journey, you'll need the following:

*   **Text Editor:** A robust text editor like VSCode or Nvim is recommended for writing and editing code and configuration files.
*   **Image Editor:** Tools such as Aseprite, Gimp, Paint.net, or Photoshop are necessary for creating and modifying spritesheets.
*   **Version Control:** Git is highly recommended for managing your mod files and tracking changes.
*   **In-Game Debugging Tools:**
    *   [Component Explorer](https://noita.wiki.gg/wiki/Mod:Component_Explorer): An invaluable mod for inspecting component values and executing Lua scripts directly within the game, essential for debugging.
    *   [Spell Lab Shugged](https://github.com/shoozzzh/Spell-Lab-Shugged): Simplifies the process of editing wands in-game, crucial for spell mod development.
    *   [Conjurer Reborn](https://github.com/KagiamamaHIna/conjurer_reborn): Allows for easy spawning of materials and entities, vital for developing enemy and material mods.

### IDE Extensions and API Definitions

For an enhanced development experience, consider these VSCode extensions and API definitions:

*   **VSCode Extensions:**
    *   [Noita API](https://marketplace.visualstudio.com/items?itemName=evaisa.vscode-noita-api): Provides Noita API support within VSCode.
    *   [Noita File Autocomplete](https://marketplace.visualstudio.com/items?itemName=Nathansnail.noita-file-autocomplete): Offers autocompletion for Noita files.
*   **Noita API Definitions for LSP:**
    *   [Noita API def](https://github.com/NathanSnail/AutoLuaAPI/blob/master/out.lua): An alternative, type-safe, and up-to-date source definition for Evaisa's Noita API. Refer to its README.md for installation instructions.
    *   [Noita XML def](https://github.com/NathanSnail/noita_xml_dtd): An XSD schema for most Noita XML files.
    *   [Noita Type Stubs](https://github.com/NathanSnail/noita_stubs): Type stubs for critical files within the `data/` directory.

    These require Lua and XML language server support:
    *   **Lua:** [Lua (VSCode)](https://marketplace.visualstudio.com/items?itemName=sumneko.lua) \| [Lua (Nvim)](https://github.com/LuaLS/lua-language-server)
    *   **XML:** [XML (VSCode)](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-xml) \| [XML (Nvim)](https://github.com/eclipse-lemminx/lemminx)

## Getting Started with Modding

The initial steps involve setting up your environment and understanding the game's file structure.

### Extracting Data Files

Noita's core assets, including spritesheets, scripts, and entity definitions, are contained within the `Noita\data\data.wak` archive. While not strictly mandatory, extracting these files provides invaluable insight into the game's structure and allows you to examine example code.

#### On Windows

1.  Locate your Noita installation folder (Steam Library -> Right-click Noita -> Manage -> Browse Local Files).
2.  Copy the contents of the `tools_modding\` folder into Noita's root directory.
3.  Run `data_wak_unpack.bat`. A terminal window will appear.
4.  A File Explorer window will open to `%UserProfile%\AppData\LocalLow\Nolla_Games_Noita\`. Bookmark or copy this folder for easy access.
5.  To view all files, including hidden ones, click the "View" button in File Explorer and check "Hidden items."

You will now have direct access to Noita's Lua code, entity XML definitions, and spritesheets.

#### On Linux

1.  In Steam, right-click Noita, go to Properties -> General, and add `-wizard_unpak` to the Launch Options.
2.  Launch Noita once. This will extract the data files to `.steam/steam/steamapps/compatdata/881100/pfx/drive_c/users/steamuser/AppData/LocalLow/Nolla_Games_Noita/`.
3.  Remove the `-wizard_unpak` launch parameter.
4.  Bookmark or copy this extracted folder for convenient access.

### Next Steps

After extracting the data files, consider the following:

*   **Modding Basics:** Review [Modding: Basics](https://noita.wiki.gg/wiki/Modding:_Basics) for fundamental concepts, debugging techniques, and best practices.
*   **Explore Example Mods:** Create a copy of the `mods\example` directory and experiment with its contents to understand the file structure and modding workflow.
*   **Consult Documentation:** Familiarize yourself with the documentation provided in the `tools_modding\` folder:
    *   `component_documentation.txt` (also available under [Category:Documentation](https://noita.wiki.gg/wiki/Category:Documentation))
    *   `lua_api_documentation.txt`
    These files are the most up-to-date resources and are essential for mod development.
*   **Study Existing Mods:** Download and examine mods created by other players from platforms like:
    *   [modworkshop.net](https://modworkshop.net/game/noita)
    *   [Steam Workshop](https://steamcommunity.com/workshop/browse/?appid=881100&)
    This is an excellent way to learn techniques and understand how different features are implemented.

## Need Help?

The [Noita Discord server](https://discord.gg/SZtrP2r) hosts a vibrant and supportive modding community. You can find dedicated channels for:

*   `#mod-discussion`
*   `#mod-development`
*   `#mod-support`
*   `#mod-showcase`
*   `#mod-releases`

Don't hesitate to join and ask questions; the community is eager to assist new modders.

---

## Core Modding Concepts

Noita's modding relies heavily on its data-driven architecture. Understanding these core concepts is key to effective mod creation.

### Entity Component System (ECS)

Noita utilizes an Entity Component System (ECS) to manage game objects. In this paradigm:

*   **Entities:** Represent distinct "things" in the game, such as enemies, projectiles, wands, items, and the player.
*   **Components:** Are modular pieces of data and functionality that are attached to entities. An entity's behavior and properties are determined by the components it possesses.

This system allows for flexible and modular design, where new behaviors can be added by simply attaching new components to existing entities or creating new entities with custom component combinations.

### Data Files: XML and Lua

The primary methods for defining and modifying game content are:

*   **XML Files:** Used for defining entities, their components, properties, and relationships. These files structure the game's data and are often the first place to look when modifying existing content or creating new entities.
*   **Lua Scripts:** Used for implementing game logic, custom behaviors, and dynamic interactions. Lua scripts can be attached to entities via components, allowing for complex scripting of gameplay mechanics.

### File Structure and Organization

When creating a mod, you will typically place your custom files within a dedicated mod folder. The structure of this folder often mirrors the game's internal structure, allowing you to override or add to existing game assets.

*   **`mods/<your_mod_name>/`**: The root directory for your mod.
*   **`mods/<your_mod_name>/data/`**: Contains custom data files, such as XML definitions for entities, items, or spells.
*   **`mods/<your_mod_name>/lua/`**: Houses your custom Lua scripts.
*   **`mods/<your_mod_name>/gfx/`**: For custom spritesheets and image assets.

### Key Data Directories and Files

After extracting `data.wak`, you'll find several important directories and files:

*   **`data/entities/`**: Contains XML files defining various entities in the game.
*   **`data/scripts/`**: Holds Lua scripts that govern game logic.
*   **`data/materials/`**: Defines the properties of different materials.
*   **`data/spells/`**: XML definitions for spells.
*   **`data/perks/`**: XML definitions for perks.
*   **`data/tags.xml`**: Defines the tag system used for entity interactions.

## Modding Guides and Resources

This section provides links to more specific guides and essential reference materials for various aspects of Noita modding.

### Fundamentals

*   [Modding: Basics](https://noita.wiki.gg/wiki/Modding:_Basics): Covers fundamental modding concepts, debugging, and best practices.
*   [Data.wak](https://noita.wiki.gg/wiki/Data.wak): Information about the game's primary data archive.
*   [Modding: Lua Scripting](https://noita.wiki.gg/wiki/Modding:_Lua_Scripting): An introduction to using Lua for modding.
*   [Modding: Useful Tools](https://noita.wiki.gg/wiki/Modding:_Useful_Tools): A list of helpful tools for mod development.

### Guides for Specific Content Types

*   [Modding: Audio](https://noita.wiki.gg/wiki/Modding:_Audio): How to modify or add custom audio.
*   [Modding: Making a custom enemy](https://noita.wiki.gg/wiki/Modding:_Making_a_custom_enemy): Step-by-step guide for creating new enemies.
*   [Modding: Making a custom environment](https://noita.wiki.gg/wiki/Modding:_Making_a_custom_environment): Guide for creating custom environments.
    *   [Modding: Fog of War](https://noita.wiki.gg/wiki/Modding:_Fog_of_War): Specific details on modifying fog of war effects.
*   [Modding: Image Emitters](https://noita.wiki.gg/wiki/Modding:_Image_Emitters): Creating custom image emitters.
*   [Modding: Making a custom material](https://noita.wiki.gg/wiki/Modding:_Making_a_custom_material): Guide for creating new materials.
*   [Modding: Making a custom perk](https://noita.wiki.gg/wiki/Modding:_Making_a_custom_perk): How to create custom perks.
*   [Modding: Special Behaviors](https://noita.wiki.gg/wiki/Modding:Special_Behaviors): Implementing unique entity behaviors.
*   [Modding: Making a custom spell](https://noita.wiki.gg/wiki/Modding:_Making_a_custom_spell): Guide for creating new spells.
*   [Modding: Making a custom spritesheet](https://noita.wiki.gg/wiki/Modding:_Making_a_custom_spritesheet): Creating and integrating custom spritesheets.
*   [Modding: Publishing mods to Steam Workshop](https://noita.wiki.gg/wiki/Modding:_Publishing_mods_to_Steam_Workshop): Instructions for uploading your mods to Steam Workshop.
*   [Modding: Using CMake](https://noita.wiki.gg/wiki/Modding:_Using_CMake): Information on using CMake for mod development.

### Components and Entities

*   [Category:Documentation](https://noita.wiki.gg/wiki/Category:Documentation): A collection of documentation pages for various components.
*   [Modding: Enums](https://noita.wiki.gg/wiki/Modding:_Enums): Lists and explanations of enumerations used in Noita.
*   [Modding: List of all tags](https://noita.wiki.gg/wiki/Modding:_List_of_all_tags): A comprehensive list of entity tags.
*   [Modding: Special tags](https://noita.wiki.gg/wiki/Modding:_Special_tags): Details on special tags and their functions.
*   [Modding: Tags System](https://noita.wiki.gg/wiki/Modding:_Tags_System): Explanation of how the tag system works.
*   [Modding: Component Update Order](https://noita.wiki.gg/wiki/Modding:_Component_Update_Order): Understanding the order in which components are updated.

### Lua Scripting

*   [Modding: Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API): Comprehensive documentation for the Noita Lua API.
*   [Modding: Utilities](https://noita.wiki.gg/wiki/Modding:_Utilities): Useful Lua utility scripts and functions.

### Other Information and References

*   [Enemy Information Table](https://noita.wiki.gg/wiki/Enemy_Information_Table): A detailed table of enemy properties.
*   [Modding: Magic Numbers](https://noita.wiki.gg/wiki/Modding:_Magic_Numbers): Explanations for various "magic numbers" used in game files.
*   [Modding: List of Sounds](https://noita.wiki.gg/wiki/Modding:_List_of_Sounds): A reference for sound event names.
*   [Modding: Spell IDs](https://noita.wiki.gg/wiki/Modding:Spell_IDs): A list of spell identifiers.
*   [Modding: Perk IDs](https://noita.wiki.gg/wiki/Modding:Perk_IDs): A list of perk identifiers.
*   [Modding: Material IDs](https://noita.wiki.gg/wiki/Modding:Material_IDs): A list of material identifiers.