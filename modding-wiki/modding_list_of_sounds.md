---
title: Noita Modding: List of Sounds
source: https://noita.wiki.gg/wiki/Modding:_List_of_Sounds
category: modding-wiki
---

# Noita Modding: List of Sounds

This documentation provides a comprehensive list of sound events available in Noita, categorized by their respective bank files. Understanding these sound events is crucial for modders looking to implement custom audio, replace existing sounds, or trigger specific audio cues within their mods.

## Usage

Sound events in Noita are organized into bank files, indicated by the list headers (e.g., `ambience`, `animals`). The full path to these bank files is typically `data/audio/Desktop/[bank_name].bank`.

*   **Events:** Most entries represent playable sound events.
*   **Snapshots:** Entries marked with a preceding asterisk (\*) are snapshots, which are often used for ambient or environmental sounds.

### Examples

#### Triggering Sounds via Lua Script

To play a sound effect at a specific location in your Lua scripts, use the `GamePlaySound` function:

```lua
GamePlaySound("data/audio/Desktop/projectiles.bank", "player_projectiles/flamethrower/create", x, y)
```

#### Attaching Sounds to Entities via XML

When defining entities in XML, you can attach sounds using the `<AudioComponent>`:

```xml
<AudioComponent
  file="data/audio/Desktop/animals.snd"
  event_root="animals/wizard"
></AudioComponent>
```

In this case, `event_root` specifies the general category of the sound, and the FMOD/Noita engine will play the appropriate sound effect when the associated in-game event triggers.

## List of Sounds

This list was generated on **2024-03-25** (after the epilogue update) using the `fevlist` tool.

### Master Bank

| GUID                                 | Event                 | Sound                                                              |
| :----------------------------------- | :-------------------- | :----------------------------------------------------------------- |
| fcb63c0a-331d-44e6-bf64-cfa8c5b6e6e7 | \*snowcave            |                                                                    |
| 53a7180c-9635-4a37-a2b8-fb8001ac66ff | \*music\_reverb       |                                                                    |
| a0219622-35b0-4a2d-8de4-650884606931 | \*vault               |                                                                    |
| 8c3abc6b-141a-42fe-9d0f-eefcf03cd52f | \*teleport\_nearby    |                                                                    |
| dadeda7a-c13b-484b-929e-d3c513e7173b | \*cave                |                                                                    |
| c9b0b78b-9869-4058-91fb-73188f7b9103 | \*underwater          |                                                                    |
| cf47a395-7b3f-4fd2-adc1-e234364460ce | \*concentration       |                                                                    |
| 2aa42396-4f12-4e40-9319-c51683cc06d1 | \*music\_duck         |                                                                    |
| fcdea7b2-610e-4ba1-b6b2-fc5196003702 | fx/fx\_concentration  | - amb\_outside\_loop1<br>- concentration\_loop                     |
| 2881eaba-a543-4c53-8dc2-8a63d3e8e84f | fx/fx\_underwater     |                                                                    |
| 310cecea-3674-4ea8-a6ac-2a8facd05638 | \*hills               |                                                                    |
| bc5e80f9-a380-47c9-8799-3e02eea94feb | \*drugged             |                                                                    |

### ambience

| GUID                                 | Event     | Sound