---
title: Video Assets
category: video
---

# Video Assets

This folder contains video assets used within Noita. These are primarily for visual effects and cutscenes.

## Key Attributes

*   **`video?`**: This attribute is crucial for the build script. Its presence indicates that the asset is a video file and needs to be processed correctly during the game's build process.

## Usage

Video assets are typically referenced by other game components, such as entities or scripts, to trigger visual sequences or animations.

## Example (Conceptual)

While specific XML or Lua examples are not provided in the source, a conceptual usage might look like this:

```lua
-- In a script that triggers a cutscene
local cutscene_video = "data/video/intro_cutscene.ogg" -- Example video file
-- ... logic to play the video ...
```

```xml
<!-- In an entity definition that uses a video for an effect -->
<Entity>
  <SomeComponent component_name="VideoPlayer" video_file="data/video/explosion_effect.ogv" />
  <!-- ... -->
</Entity>
```