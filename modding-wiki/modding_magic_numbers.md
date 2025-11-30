---
title: Noita Modding: Magic Numbers
source: https://noita.wiki.gg/wiki/Modding:_Magic_Numbers
category: modding-wiki
---

# Noita Modding: Magic Numbers

This documentation details the "magic numbers" used within the Noita game engine. These numbers control a wide array of game mechanics, from physics and rendering to UI elements and gameplay behaviors. Understanding and modifying these values is crucial for advanced modding, allowing for deep customization of the game's core functionality.

## Understanding Magic Numbers

Magic numbers are numerical or boolean values embedded directly into the game's code that influence various game systems. They can be modified by placing a `magic_numbers.xml` file within a mod's `data/` directory or by using the `ModMagicNumbersFileAdd` Lua function. This page serves as a comprehensive reference for these values.

### Format

Magic number XML files follow a simple structure:

```xml
<MagicNumbers
  PROPERTY1="VALUE1"
  PROPERTY2="VALUE2"
  >
</MagicNumbers>
```

## Magic Number Reference

The following table lists the magic numbers defined in the game engine, their types, default values, and descriptions.

| Name                                                     | Type   | Default Value                               | Description