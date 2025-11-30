---
title: Modding: Audio
source: https://noita.wiki.gg/wiki/Modding:_Audio
category: modding-wiki
---

# Modding: Audio

This documentation covers how to manage audio within Noita mods. It details the process of extracting existing game sound files, replacing them with custom audio, and adding entirely new sound effects to your mods. Understanding Noita's audio system is crucial for creating immersive and polished modded experiences.

## Extracting Existing Audio

Noita's audio files are stored in `.wav` format, compressed within `.bank` files. These are located in the `Steam\steamapps\common\Noita\data\audio\Desktop\` directory.

To extract these files:

1.  **Download FMOD Bank Tools:** Obtain the "Fmod bank tools.zip" from the Noita Discord server. You can find it in a thread related to audio modding (a specific Discord thread link was provided in the original source).
2.  **Locate Target Bank:** Identify the `.bank` file you wish to extract (e.g., `event_cues.bank`). Copy this file into the bank folder within the extracted "Fmod bank tools.zip".
3.  **Configure FMOD Bank Tools:**
    *   Run `Fmod Bank Tools.exe`.
    *   Set the `Bank Source Folder` to the full path of the folder containing your target `.bank` file (within the extracted zip).
    *   Set the `Wav Destination Folder` to a folder where you want the extracted `.wav` files to be saved (also within the extracted zip).
4.  **Extract Audio:** Click the "Extract" button in the tool. This will extract all audio files from the selected `.bank` file into your specified destination folder.

## Replacing Existing Audio

There are two primary methods for replacing default audio files in Noita:

### Method 1: Overwriting `.bank` Files

This method involves replacing the original `.bank` files with your modified versions.

*   **Process:**
    1.  Follow the steps to [extract existing audio](https://noita.wiki.gg/wiki/Modding:_Audio#Extracting_existing_audio).
    2.  Replace any `.wav` files you wish to modify.
    3.  Edit the `bankname.txt` file in the extracted `.wav` folder to correctly name your sounds.
    4.  In `Fmod Bank Tools.exe`, click "Rebuild" to create a new `.bank` file. You can generally ignore any errors by clicking "Ok".
    5.  Place your modified `.bank` file in your mod's directory at the same path as the original file you are replacing. For example: `mods/yourmod/data/audio/Desktop/animals.bank`.
    6.  Test in-game.

*   **Drawbacks:**
    *   **Fixed Length:** You cannot change the length of a sound event. If the original sound is 1 second and yours is 3 seconds, your audio will be cut off after 1 second.
    *   **Inherited Effects:** Any effects applied to the original sound will also be applied to your replacement sound.
    *   **Mod Compatibility:** This method is not compatible with other mods that attempt to replace sounds from the same `.bank` file, as only one mod can overwrite a specific file at a time.

### Method 2: GUID Replacement (Potentially Obsolete)

This method aims to trick the game into using your custom sound event instead of the original one by replacing the original sound's GUID with yours.

*   **Process:**
    1.  **Create Custom Audio:** Create your own sounds and one additional "dummy" sound.
    2.  **Build Custom `.bank`:** Build your custom `.bank` file using FMOD Studio.
    3.  **Export GUIDs:** Export the `GUIDs.txt` file from your custom `.bank`. Note the GUIDs of your custom sound events.
    4.  **Use GUID Replacer Tool:** Download and use the [FmodBankGUIDReplacer](https://github.com/TheHorscht/FmodBankGUIDReplacer) tool. This tool allows you to replace the GUIDs within your `.bank` file with the GUIDs of the sounds you want to replace. **Crucially, do not replace the GUID of your dummy sound.**
    5.  **Place `.bank` File:** Place your modified `.bank` file in your mod folder.
    6.  **Call in `init.lua`:** In your mod's `init.lua`, call `GamePlaySound("mods/your_mod/audio/your_audio.bank", "dummy_sound", 0, 0)`. This must be executed *before* the sound you want to replace is played.

*   **Example Usage of GUID Replacer:**
    Let's say your `GUIDs.txt` contains:

    ```
    ... other stuff
    {f7bc4133-a97d-487e-a7a9-b28303f90ffb} event:/boop
    {c7d655d8-ec85-4d25-bc91-cf2cca64fbb7} event:/dummy_sound
    ... more stuff
    ```

    And you want to replace `event_cues/game_over_stats/create` (GUID: `{3c831728-2d37-4b80-bc78-b4d069164ebc}`). You would use the tool like this:

    `guid_replacer.exe your_audio.bank {f7bc4133-a97d-487e-a7a9-b28303f90ffb} {3c831728-2d37-4b80-bc78-b4d069164ebc}`

    **Remember: Do not replace the GUID of your dummy sound.**

## Creating Custom Audio for Noita

Noita utilizes [FMOD Studio](https://www.fmod.com/) (version 2.01.05) for its sound engine. The core concept involves defining FMOD "bank" files that contain all your sound effects and assigning individual "events" to each sound. These events are then referenced in XML or Lua scripts to trigger the playback of your custom sounds.

Refer to these directories for guidance:

*   `Noita/tools_modding/noita-fmod-project/`
*   `Noita/mods/example/`

### Setup

1.  Ensure the `noita-fmod-project` folder is present in your Noita installation directory.
2.  Install FMOD Studio version 2.01.05 from the official FMOD website.

### FMOD Studio Workflow

1.  **Open Project:** Open `noita-mods.fspro` in FMOD Studio. You should find a `snd_mod` folder containing an example `create` event. Common event types to be aware of are `create` and `loop`.
2.  **Examine Events:** Clicking the `create` event within `snd_mod` will reveal an example sound like `worm_attack_bite_01`. This sound might be in "Async" mode, utilize randomization for pitch, and have "Distance" and "lowpass" parameters for in-game effects like volume fading.
3.  **Routing Groups & Effects:** Noita employs various Routing Groups to apply audio effects like reverb and equalization. Access these by navigating to `Window` > `Mixer`. You can then move your sounds into appropriate groups, such as `game_sfx`, which contains `snd_mod/create`. This group is frequently used.
4.  **Assign to Bank:** To make a sound usable by Noita, it must be added to a Bank. Right-click the event, select `Assign to Bank`, and choose the desired bank (avoiding "Master Bank" if possible).
5.  **Build Project:** After setting up your sounds and assigning them to banks, build your FMOD project by going to `File` > `Build`.
6.  **Export GUIDs:** Noita needs references to your bank's sounds. Go to `File` > `Export GUIDs`. This will generate a `GUIDs.txt` file.

### Integrating into Noita

1.  **Copy Files:**
    *   Copy the generated `GUIDs.txt` file from `noita-fmod-project/Build` into your mod's directory.
    *   Copy the `.bank` file you created (excluding "Master Bank") from `noita-fmod-project/Build/Desktop` into your mod's directory.
2.  **Register Audio Mappings:** Open your mod's `init.lua` file and add the following line, replacing the path with the actual location of your `GUIDs.txt` file:

    ```lua
    ModRegisterAudioEventMappings("mods/modname/directory/to/GUIDs.txt")
    ```

3.  **Add Audio Components:** In any XML files where you want to use your custom sounds, add the appropriate `AudioComponent` or `AudioLoopComponent`, depending on the type of event you created in FMOD.

    **Example `AudioComponent` for a projectile:**

    ```xml
    <AudioComponent
           file="mods/modname/directory/to/bankname.snd"  <!-- Note: .bank is replaced with .snd -->
           event_root="foldername/eventname"              <!-- Refers to the FMOD event folder and event name -->
           set_latest_event_position="1"
    ></AudioComponent>
    ```

4.  **Test In-Game:** Launch Noita to experience your custom audio.

## List of All Default Sound Effects

For a comprehensive list of default sound effects, please refer to: [Modding: List of Sounds](https://noita.wiki.gg/wiki/Modding:_List_of_Sounds) (Note: This list may currently be incomplete).