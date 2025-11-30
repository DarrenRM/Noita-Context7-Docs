---
title: Modding: Using CMake
source: https://noita.wiki.gg/wiki/Modding:_Using_CMake
category: modding-wiki
---

# Modding: Using CMake

This documentation explains how to leverage CMake, a powerful build system primarily used for C and C++ development, to automate various aspects of your Noita modding workflow. It's particularly useful for advanced modding requirements such as creating release packages, downloading external dependencies, generating files, compiling native code, and running tests, streamlining your mod development process.

## Installation

To begin using CMake for your Noita mods, you'll need to install CMake and optionally Ninja.

*   **CMake:** [https://cmake.org/install/](https://cmake.org/install/)
*   **Ninja:** [https://ninja-build.org/](https://ninja-build.org/) (Recommended generator for this guide)

Ensure that both CMake and Ninja are added to your system's `PATH` environment variable for easy access from the command line.

## Basics of CMake for Noita Mods

This section covers the fundamental steps of setting up a basic Noita mod project using CMake.

### Project Start

Let's create a simple mod named "HelloMod" to demonstrate the project structure and initial CMake configuration.

**Project Structure:**

```
HelloMod-source/
├── CMakeLists.txt
└── HelloMod
    ├── init.lua
    └── mod.xml
```

The `HelloMod` directory contains files that will be directly copied into the final mod folder. Files that require processing or are not meant for the release package should be placed outside this directory.

The `CMakeLists.txt` file defines the build process. Here's a basic configuration for an installable project:

```cmake
cmake_minimum_required(VERSION 3.24)

project(HelloMod
    VERSION 0.1.0
    DESCRIPTION "Noita example mod"
    HOMEPAGE_URL "https://github.com/dextercd/Noita-CMake-Example"
    LANGUAGES # Empty
)

install(DIRECTORY HelloMod
    DESTINATION .
    COMPONENT HelloMod
)
```

*   `cmake_minimum_required`: Specifies the minimum required CMake version.
*   `project`: Defines basic project information like name, version, description, and homepage.
*   `install(DIRECTORY ...)`: Configures the specified directory to be copied to the installation location during the install step.

**Build and Install Commands:**

These commands are typically run from a separate build directory.

```bash
# Configure the build (replace paths as needed)
cmake -G Ninja -DCMAKE_INSTALL_PREFIX="C:\Program Files (x86)\Steam\steamapps\common\Noita\mods" -B Y:\HelloMod-build -S Y:\HelloMod-source

# Navigate to the build directory
cd Y:\HelloMod-build

# Build the project (detects changes and updates build files)
cmake --build .

# Install the mod to the specified prefix
cmake --install . --component HelloMod
```

The first command configures the build, specifying the source and build directories. The `--build` subcommand updates build files, and `--install` copies the mod files to the `CMAKE_INSTALL_PREFIX`, which is set to your Noita mods folder for development convenience.

### Creating a Package

CMake's CPack module can automate the creation of release archives for your mod.

Add the following to your `CMakeLists.txt` file, typically before any CPack-specific includes:

```cmake
# Packaging

set(CPACK_GENERATOR ZIP)
set(CPACK_INCLUDE_TOPLEVEL_DIRECTORY FALSE)
set(CPACK_PACKAGE_FILE_NAME "${PROJECT_NAME}-${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}")
set(CPACK_VERBATIM_VARIABLES TRUE)
include(CPack)
```

*   `CPACK_GENERATOR`: Sets the package format (e.g., `ZIP`, `7Z`, `TGZ`).
*   `CPACK_INCLUDE_TOPLEVEL_DIRECTORY`: Prevents an extra top-level directory in the archive.
*   `CPACK_PACKAGE_FILE_NAME`: Defines the naming convention for the package file.
*   `CPACK_VERBATIM_VARIABLES`: Ensures variables are handled literally.

After adding this and re-running the build and install steps, you can create a zip archive of your mod:

```bash
# From the build directory
cpack
```

This will generate a zip file (e.g., `HelloMod-0.1.0.zip`) containing your mod files, ready for distribution. You can specify a different generator with `cpack -G 7Z`.

### Downloading Files

CMake's `FetchContent` module allows you to automatically download external files or archives as dependencies for your mod.

Add the following to your `CMakeLists.txt` to include dependencies like EZWand and LuaJIT-MinHook:

```cmake
# Dependencies

include(FetchContent)

FetchContent_Declare(EZWand
    URL https://github.com/TheHorscht/EZWand/releases/download/v1.5.0/EZWand.lua
    DOWNLOAD_NO_EXTRACT TRUE
)
FetchContent_MakeAvailable(EZWand)

install(FILES ${ezwand_SOURCE_DIR}/EZWand.lua
    DESTINATION HelloMod/lib/EZWand
    COMPONENT HelloMod
)

FetchContent_Declare(LuaJIT-MinHook
    URL https://github.com/dextercd/LuaJIT-MinHook/releases/download/release-1.1.1/LuaJIT-MinHook-1.1.1.zip
)
FetchContent_MakeAvailable(LuaJIT-MinHook)

install(DIRECTORY ${luajit-minhook_SOURCE_DIR}/
    DESTINATION HelloMod/lib/MinHook
    COMPONENT HelloMod
)
```

*   `FetchContent_Declare`: Defines a dependency by its name and download URL. Use `DOWNLOAD_NO_EXTRACT TRUE` for single files.
*   `FetchContent_MakeAvailable`: Downloads the content and makes it available.
*   `install`: Copies the downloaded files into your mod's structure. The `${<lowercaseName>_SOURCE_DIR}` variable points to the downloaded files.

After building and packaging, your mod archive will include these downloaded dependencies.

### Building C/C++ Code

CMake excels at building native code (executables and DLLs) for your mod. This is useful for tasks like data generation, performance-critical operations, or integrating external libraries.

To build C/C++ code, you first need a C/C++ toolchain installed (e.g., Visual Studio's C++ build tools). Ensure CMake can find it, often by launching your command prompt from the toolchain's environment (e.g., "x86 Native Tools Command Prompt" for VC++).

Modify your `project` command in `CMakeLists.txt` to include C++ support:

```cmake
 project(HelloMod
     VERSION 0.1.0
     DESCRIPTION "Noita example mod"
     HOMEPAGE_URL "https://github.com/dextercd/Noita-CMake-Example"
+    LANGUAGES CXX
 )
```

Create a `clipboard.cpp` file with the following content to enable clipboard functionality:

```cpp
#define WIN32_LEAN_AND_MEAN
#include <windows.h>
#include <cstring>

/**
 * Set the clipboard to the provided text.
 * @return true if the clipboard change was successful.
 */
extern "C" __declspec(dllexport)
bool set_clipboard(const char* text)
{
    bool success = false;
    bool clipboard_opened = false;
    HGLOBAL global_data = nullptr;
    // Need a window for the clipboard API, it's never made visible
    HWND clipboard_window = CreateWindowA(
        "Message", nullptr, 0, 0, 0, 0, 0, nullptr, nullptr, nullptr, nullptr);
    if (!clipboard_window)
        goto cleanup;
    if (!(clipboard_opened = OpenClipboard(clipboard_window)) || !EmptyClipboard())
        goto cleanup;
    std::size_t data_length = std::strlen(text) + 1;
    global_data = GlobalAlloc(GMEM_MOVEABLE, data_length);
    if (!global_data)
        goto cleanup;
    void* data = GlobalLock(global_data);
    if (!data)
        goto cleanup;
    std::memcpy(data, text, data_length);
    if (!GlobalUnlock(global_data))
        goto cleanup;
    if (SetClipboardData(CF_TEXT, global_data)) {
        global_data = nullptr; // System now manages the data
        success = true;
    }
cleanup:
    if (global_data)
        GlobalFree(global_data);
    if (clipboard_opened)
        CloseClipboard();
    if (clipboard_window)
        DestroyWindow(clipboard_window);
    return success;
}
```

Add the following to your `CMakeLists.txt` to build this C++ code into a DLL and install it:

```cmake
# C++ module

add_library(clipboard MODULE
    clipboard.cpp
)

install(TARGETS clipboard
    LIBRARY DESTINATION HelloMod/dll
    COMPONENT HelloMod
)
```

Your `mod.xml` should have `request_no_api_restrictions="1"` enabled. The `init.lua` would then use LuaJIT's `ffi` module to load and call the DLL function:

```lua
local ffi = require("ffi")

ffi.cdef([[\
bool set_clipboard(const char* text);\
]])

local clipboard = ffi.load("mods/HelloMod/dll/clipboard.dll")

function OnWorldInitialized()
    local seed = StatsGetValue("world_seed")
    local text = "Currently playing this seed: " .. seed
    if not clipboard.set_clipboard(text) then
        GamePrint("Couldn't set clipboard!")
    end
end
```

This setup allows your mod to interact with the system clipboard, for example, by automatically copying the world seed.

## Project Using CMake

Here are some Noita mods that utilize CMake, providing examples and reusable code snippets:

*   [Noita-CMake-Example](https://github.com/dextercd/Noita-CMake-Example) - The example project used throughout this guide.
*   [Noita-Minidump](https://github.com/dextercd/Noita-Minidump) - Demonstrates building C++ code and integrating DLLs into mods.
*   [Noita-Shutdown](https://github.com/dextercd/Noita-Shutdown) - Shows generating sprite images using Python scripts managed by CMake.
*   [Noita-Synchronise-Expansive-Worlds](https://github.com/dextercd/Noita-Synchronise-Expansive-Worlds) - Involves building C and C++ code and generating documentation files.
*   [Noita-Component-Explorer](https://github.com/dextercd/Noita-Component-Explorer) - Illustrates generating Lua code from templates.

## Resources

This guide provides a practical introduction to using CMake for Noita modding. For comprehensive understanding, refer to the official CMake documentation and other learning resources.

*   **CMake Reference Documentation:** [https://cmake.org/cmake/help/latest/](https://cmake.org/cmake/help/latest/)
*   **Professional CMake Book:** [https://crascit.com/professional-cmake/](https://crascit.com/professional-cmake/)