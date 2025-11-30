---
title: Special Behaviors
source: https://noita.wiki.gg/wiki/Modding:Special_Behaviors
category: modding-wiki
---

# Special Behaviors

This documentation details various special behaviors associated with objects, components, and other entities within Noita. Understanding these behaviors is crucial for modders looking to create custom items, modify existing ones, or implement unique game mechanics.

## Orbs

Noita features 12 distinct orbs that can be obtained during a normal playthrough, with an additional one from a Great Treasure Chest. Each orb is assigned a unique `orb_id` within its `OrbComponent`. Naturally spawned orbs have IDs from 0 to 10, while the Great Treasure Chest orb has an ID of 11. Orbs located in parallel worlds have their IDs adjusted: West parallel world orbs have their IDs increased by 128, and East parallel world orbs have their IDs increased by 256. The game determines the world of an orb by checking its position relative to a bounding box defined by (`X-17920, Y-7166`) and (`X+17920, Y+17408`). Orbs outside this box are considered in a parallel world, with negative X positions indicating the West world and positive X positions indicating the East world.

An `OrbComponent` can be attached to any item. When an item with an `OrbComponent` is picked up for the first time in a run, it increments the player's orb counter. Subsequent pickups of items with the same `orb_id` will not increase the counter. If a custom orb is created with an `orb_id` that matches one of the 12 standard orbs, the player will be unable to collect the original orb, and its visual representation will be replaced with a blank orb. Picking up a custom orb with an `orb_id` that does not correspond to any existing orb will still increment the counter and create a flag in the save file's `persistent/orbs_new` folder, named after the orb's ID.

Due to the `CameraBoundComponent`, orbs despawn when the player moves too far away and respawn when they approach. This respawn process re-initializes the orb's `orb_init.lua` script. Modders can append their own scripts to `orb_init.lua` to execute custom logic whenever an orb respawns.

### Orb IDs

The following table lists the different orbs and their corresponding `orb_id` values for the main world, West parallel world, and East parallel world.

| Description | Main World ID | West World ID | East World ID |
|---|---|---|---|
| [Floating Island](https://noita.wiki.gg/wiki/Forest#The_Floating_Island "Forest") Orb | 0 | 128 | 256 |
| [Pyramid](https://noita.wiki.gg/wiki/Pyramid "Pyramid") Orb | 1 | 129 | 257 |
| [Frozen Vault](https://noita.wiki.gg/wiki/Frozen_Vault "Frozen Vault") Orb | 2 | 130 | 258 |
| [Lava Lake](https://noita.wiki.gg/wiki/Lava_Lake "Lava Lake") Orb | 3 | 131 | 259 |
| [Sandcave](https://noita.wiki.gg/wiki/Sandcave "Sandcave") Orb | 4 | 132 | 260 |
| [Magical Temple](https://noita.wiki.gg/wiki/Magical_Temple "Magical Temple") Orb | 5 | 133 | 261 |
| [Lukki Lair](https://noita.wiki.gg/wiki/Lukki_Lair "Lukki Lair") Orb | 6 | 134 | 262 |
| [Abyss Orb Room](https://noita.wiki.gg/wiki/Lava_Lake#Orb_room "Lava Lake") | 7 | 135 | 263 |
| [The Work (Hell)](https://noita.wiki.gg/wiki/The_Work_(Hell) "The Work (Hell)") Orb | 8 | 136 | 264 |
| [Snowy Chasm](https://noita.wiki.gg/wiki/Snowy_Chasm "Snowy Chasm") Orb | 9 | 137 | 265 |
| [Wizard's Den](https://noita.wiki.gg/wiki/Wizard%27s_Den "Wizard's Den") Orb | 10 | 138 | 266 |
| [Great Treasure Chest](https://noita.wiki.gg/wiki/Great_Treasure_Chest "Great Treasure Chest") Orb | 11 | 139 | 267 |