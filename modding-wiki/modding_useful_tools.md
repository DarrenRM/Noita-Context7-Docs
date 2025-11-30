---
title: Noita Modding: Useful Tools
source: https://noita.wiki.gg/wiki/Modding:_Useful_Tools
category: modding-wiki
---

# Noita Modding: Useful Tools

This documentation compiles a collection of helpful tools, frameworks, and mods that can significantly aid Noita modders in their development process. Utilizing these resources can streamline workflows, provide essential utilities, and offer insights into the game's mechanics, ultimately leading to more efficient and effective mod creation.

## Useful Mods

These mods are designed to be integrated into your game and provide functionalities that are beneficial for modding and testing.

*   **CheatGUI** [Steam](https://steamcommunity.com/sharedfiles/filedetails/?id=1984977713)
    *   A basic cheat/dev menu for testing various aspects within the normal game world.
*   **Conjurer Reborn** [Steam](https://steamcommunity.com/sharedfiles/filedetails/?id=3390660504)
    *   An unofficial version of Conjurer, authorized by the original creators.
    *   Provides a clean sandbox mode with separate save slots.
    *   Includes special features for modders: display hitboxes and ragdoll positions, and easily spawn custom entities.
*   **Mod:Component Explorer**
    *   Offers an entity/component viewer, a Lua console, and in-game logging capabilities.
*   **Enable Logger** [Steam](https://steamcommunity.com/workshop/filedetails/?id=2124936579)
*   **Alchemy Lib** [Steam](https://steamcommunity.com/sharedfiles/filedetails/?id=2263831584)
    *   A library mod for adding randomized alchemy recipes.

## Frameworks

Frameworks, libraries, and wrappers that can be included in your mod's code to provide pre-built functionalities.

*   **EZWand** [GitHub](https://github.com/TheHorscht/EZWand)
    *   A wand building framework and utility.
*   **DialogSystem** [GitHub](https://github.com/TheHorscht/DialogSystem)
    *   A library for adding dialogue to game elements.
*   **StringStore** [GitHub](https://github.com/zatherz/StringStore)
    *   Allows reading and writing complex data structures into the Noita globals API.
*   **LuaNXML** [GitHub](https://github.com/NathanSnail/luanxml)
    *   A library for reading and writing Noita XML files using Lua.
*   **Noita Dear ImGui** [GitHub](https://github.com/dextercd/Noita-Dear-ImGui)
    *   An alternative GUI library for Noita.
*   **Noita Parallax** [Github](https://github.com/alex-3141/noita-parallax)
    *   A tool for creating parallax backgrounds in Noita.
*   **FMOD Audio System** [Github](https://github.com/EvaisaDev/evaisa.audiosystem)
    *   An FMOD wrapper for \*unsafe\* mods, enabling 3D audio with multiple sources. It can directly play audio files or samples.
*   **Starting Potion Lib** [GitHub](https://github.com/FatalUserK/noita_lib-potion_starting)
    *   A library that simplifies appending to the `potion_starting.lua` file, reducing mod incompatibilities.

## External Tools

These are tools that are not directly integrated into a mod's codebase but are valuable for development and analysis.

*   [https://thehorscht.github.io/NoitaWangTiler/](https://thehorscht.github.io/NoitaWangTiler/)
    *   A web-based Wang tile previewer.
*   [https://github.com/ryyst/noita-utils](https://github.com/ryyst/noita-utils)
    *   Utilities for splicing and stitching character spritesheets, useful for importing into Aseprite.
    *   Can generate the [materials image reference](https://noita.wiki.gg/wiki/File:Material_Colors.png).
*   [https://github.com/zatherz/fevlist](https://github.com/zatherz/fevlist)
    *   A small tool to list event paths from FMOD `.bank` files.
*   [https://marketplace.visualstudio.com/items?itemName=evaisa.vscode-noita-api](https://marketplace.visualstudio.com/items?itemName=evaisa.vscode-noita-api)
    *   A VSCode extension providing Noita API autocompletion.
*   [https://marketplace.visualstudio.com/items?itemName=Nathansnail.noita-file-autocomplete](https://marketplace.visualstudio.com/items?itemName=Nathansnail.noita-file-autocomplete)
    *   A VSCode extension for Noita file autocompletion and validation.
*   [https://github.com/Glooore/noita-gif-generator](https://github.com/Glooore/noita-gif-generator)
    *   A script for generating GIFs using an XML file with animation data.
*   [https://github.com/NathanSnail/wisper](https://github.com/NathanSnail/wisper)
    *   A tool for calculating optimal wisp solutions.
*   [https://github.com/NathanSnail/formation_finder](https://github.com/NathanSnail/formation_finder)
    *   A tool for calculating optimal formation angles for LDT (Limited Damage Threshold).
*   [https://github.com/Ko0bEy/Noita-Speed-Calculator](https://github.com/Ko0bEy/Noita-Speed-Calculator)
    *   A tool for calculating speed stacks for LDT.

### Typefaces

*   **NoitaPixel.ttf**
    *   The official Noita font.
    *   [Download](https://commons.wiki.gg/File:NoitaPixel.ttf)
*   **NoitaGlyphScaled.ttf**
    *   The Noita Glyph font.
    *   [Download](https://commons.wiki.gg/File:NoitaGlyphScaled.ttf)
*   **Noita Blackletter**
    *   A gothic typeface inspired by Noita.
    *   [Reddit Post](https://www.reddit.com/r/noita/comments/jp56ub/a_while_ago_i_made_noita_blackletter_this_is_now/)
    *   [Dropbox Download](https://www.dropbox.com/s/gl7u3w22tr859m5/Noita%20Blackletter-Regular%20%28new%29.zip?dl=0)
    *   [![Example Noita Blackletter text](https://noita.wiki.gg/images/NoitaBlackletter-Regular-example.png?a32e49)](https://noita.wiki.gg/wiki/File:NoitaBlackletter-Regular-example.png)
*   **Noita Logo Font**
    *   The font used for the Noita logo (non-vector, .psd format).
    *   [Discord Link](https://discord.com/channels/453998283174576133/645330834215141376/823963852105318400)
    *   [![An example of the noita logo font](https://noita.wiki.gg/images/thumb/Noita-logo-font-example.png/99px-Noita-logo-font-example.png?5fae6e)](https://noita.wiki.gg/wiki/File:Noita-logo-font-example.png)
*   **rust_noita_font** [GitHub](https://github.com/NathanSnail/rust_noita_font)
    *   A tool for converting TTF fonts into Noita's XML font format. Requires building from source.
*   **CustomFont Mod** [GitHub](https://github.com/KagiamamaHIna/CustomFont)
    *   A mod that converts vector font formats (like TTF) to Noita's BIN format. It can be used via a pre-compiled EXE or directly with the C++ code.

## Player Tools

These tools are primarily for players but can offer insights useful for modders, especially regarding game state and data.

*   **Noited** [https://kamiheku.github.io/noited/](https://kamiheku.github.io/noited/)
    *   A Noita death visualizer. See also [Biomes#Death visualizer](https://noita.wiki.gg/wiki/Biomes#Death_visualizer).
*   **Alter\_ukko's noita-util** [gitlab](https://gitlab.com/alter_ukko/noita-util)
    *   Includes:
        *   Save file manager (uses zip archives).
        *   Seed runner (mod-free).
        *   Noita.exe memory usage warning.
        *   Quick spell reference with search.
        *   Salakieli file decrypter.
        *   Bone folder wand browser. See [Kummitus#Examine your bones](https://noita.wiki.gg/wiki/Kummitus#Examine_your_bones).
*   **noitastats** [GitHub](https://github.com/Bullhoff/noitastats)
    *   Primarily for saving copies of `player.xml` and `world_state.xml` to track game progress. Can also be used for viewing XML and Lua files in the data and `save_00` folders.
*   **Salakieli Online File Editor** [https://www.lightbourn.net/games/Noita/editor.html](https://www.lightbourn.net/games/Noita/editor.html)
    *   An online editor for Salakieli files.
*   **Cauldron Forecast** [https://sdlwdr.github.io/cauldron_forecast/](https://sdlwdr.github.io/cauldron_forecast/)
    *   Displays the predicted content of cauldrons for upcoming days.
*   **Cessation Message Generator** [https://kaliuresis.github.io/cessation_generator/](https://kaliuresis.github.io/cessation_generator/)
    *   A tool for generating Noita's cessation messages.

### Wand Tools

*   **Noita Wand Simulator** [https://tinker-with-wands-online.vercel.app](https://tinker-with-wands-online.vercel.app/)
    *   More information available at [Tool: Noita Wand Simulator](https://noita.wiki.gg/wiki/Tool:_Noita_Wand_Simulator).
*   **Soler's Noita-loadouts** [https://soler91.github.io/noita-loadouts/#/wand-builder](https://soler91.github.io/noita-loadouts/#/wand-builder)
    *   Allows building wands and downloading them as simple game mods.
    *   *Note: This tool may be outdated and not include all spells, but it remains useful.*

### Seed Tools

*   **TwoAbove's Noitool**
    *   Main branch: [https://www.noitool.com/](https://www.noitool.com/)
    *   Beta branch: [https://dev.noitool.com/](https://dev.noitool.com/)
*   **Cr4xy's Noita Seed Tool** [https://cr4xy.dev/noita/index.html](https://cr4xy.dev/noita/index.html)
    *   *Warning: The Fungal shift display is out of date as of Epilogue 2. Use Noitool for accurate shift results.*
*   **Noita Alchemy Recipes** [https://neffc.github.io/narg/](https://neffc.github.io/narg/)
*   **Kaliuresis's Noita Orb Atlas** [https://kaliuresis.github.io/noa/](https://kaliuresis.github.io/noa/)
*   **kylixir's Greater Chest Sampo Atlas** [https://kylixir.github.io/noaSampo/](https://kylixir.github.io/noaSampo/)
    *   A modified version of the Orb Atlas site, specifically for finding Sampo chests. Useful for maximizing achievements in a single run.
*   **pudy248's Noita Wand (and Potion) Atlas** [https://pudy248.github.io/noitaWandAtlas/](https://pudy248.github.io/noitaWandAtlas/)
    *   Another copy of the Orb Atlas site, adapted to find wands of unusual sizes and specific materials from random flasks.