---
title: Publishing Mods to Steam Workshop
source: https://noita.wiki.gg/wiki/Modding:_Publishing_mods_to_Steam_Workshop
category: modding-wiki
---

# Publishing Mods to Steam Workshop

This documentation outlines the essential steps and requirements for publishing your Noita mods to the Steam Workshop. Understanding these guidelines ensures your mods are correctly packaged, uploaded, and discoverable by other players.

## Preparation

To publish your mod, you need the Steam version of Noita.

### Mod Folder Structure

1.  Your mod's folder must be located within the `Noita\mods\` directory.

### `workshop.xml` Configuration

Create a file named `workshop.xml` inside your mod's folder with the following content:

```xml
<Mod
    name="YOUR_MOD_NAME_HERE"
    description="YOUR_MOD_DESCRIPTION_HERE"
    tags="TAGS"
    dont_upload_folders="FOLDER_TO_IGNORE1|FOLDER_TO_IGNORE2"
    dont_upload_files="FILE_TO_IGNORE1|FILE_TO_IGNORE2"
    >
</Mod>
```

**Explanation of elements:**

*   `name`: Replace `YOUR_MOD_NAME_HERE` with the actual name of your mod.
*   `description`: Replace `YOUR_MOD_DESCRIPTION_HERE` with a brief description of your mod. This field can be left empty if you prefer to set the description directly on the Steam Workshop page. The description in `workshop.xml` is not updated if left empty.
*   `tags`: A comma-separated list of tags that apply to your mod.

    **Available Tags:**
    *   gameplay
    *   graphics
    *   quality of life
    *   translations
    *   perks
    *   spells
    *   player characters
    *   loadouts
    *   biomes
    *   total conversions
    *   game modes
    *   creatures
    *   bosses
    *   alchemy
    *   tweaks
    *   items
    *   audio
    *   cheats
    *   funny
    *   streaming integration
    *   mod dependencies

    Tag names must be spelled exactly as listed above and in lowercase.

*   `dont_upload_folders`: A pipe-separated list (`|`) of folders within your mod directory that should *not* be uploaded to Steam Workshop. For example: `dont_upload_folders="ignore_this|files\ignore_this_subfolder"`.
*   `dont_upload_files`: A pipe-separated list (`|`) of files within your mod directory that should *not* be uploaded to Steam Workshop. For example: `dont_upload_files="secret_dev_file.txt"`.

### Preview Image

Create a file named `workshop_preview_image.png` inside your mod's folder. This image will serve as the preview for your mod on the Steam Workshop. It should have a 16:9 aspect ratio.

### Additional Notes

*   Mods with the attribute `request_no_api_restrictions="1"` will not function correctly when uploaded through Steam Workshop.
*   Only the following file types are uploaded to Steam Workshop:
    *   `.txt`
    *   `.csv`
    *   `.xml`
    *   `.json`
    *   `.bmp`
    *   `.png`
    *   `.lua`
    *   `.frag`
    *   `.vert`
    *   `.bank`
    *   `.bin`
    *   `.plz`
*   Git folders (e.g., `.git`) are automatically ignored.
*   If you remove your mod from Steam Workshop and intend to re-upload it later, you must first delete the `workshop_id.txt` file from your mod folder. An error message like `"Steam - workshop upload failed: 2"` can indicate this issue.

## Uploading Using the Upload Wizard

1.  Ensure you are logged into your Steam account.
2.  Open a command line and navigate to your Noita installation directory.
3.  Execute the following command. Alternatively, you can use the `workshop_upload.bat` file that is shipped with the game:

    ```bash
    noita_dev.exe -workshop_upload
    ```

This will launch the interactive upload wizard.

### Batch Upload

For automated uploads without user interaction:

1.  Ensure you are logged into your Steam account.
2.  Open a command line and navigate to your Noita installation directory.
3.  Run the following command:

    ```bash
    noita_dev.exe -workshop_upload MOD_NAME -workshop_upload_change_notes CHANGE_NOTES
    ```

    *   Replace `MOD_NAME` with the name of your mod's folder (e.g., `nightmare`).
    *   Replace `CHANGE_NOTES` with the update's change notes. You can leave this empty if there are no specific notes.

This command allows for uploading mods and their updates without prompts from the uploader UI.