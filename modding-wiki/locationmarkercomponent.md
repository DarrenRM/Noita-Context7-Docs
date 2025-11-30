---
title: LocationMarkerComponent
source: https://noita.wiki.gg/wiki/Documentation:LocationMarkerComponent
category: modding-wiki
---

# LocationMarkerComponent

This documentation page details the `LocationMarkerComponent` in Noita, a crucial component for defining and managing in-game locations. Understanding this component is essential for modders who wish to create custom areas, control entity spawning within specific zones, or implement location-based game mechanics.

## Overview

The `LocationMarkerComponent` is attached to entities that serve as markers for specific locations within the game world. These markers are primarily used by the game's internal systems to identify and categorize different biomes and areas, influencing various gameplay elements such as enemy spawns, environmental effects, and quest triggers. By modifying or creating entities with this component, modders can exert fine-grained control over the game's environment and its inhabitants.

## Component Properties

The `LocationMarkerComponent` has several properties that define the characteristics of the location it represents. These properties are typically configured within the entity's XML definition.

### `biome`

This property specifies the biome associated with the location marker. The game uses this information to determine which biome-specific assets and behaviors should be active in this area.

**Data Type:** String

**Possible Values:**

| Biome ID | Description                                     |
| :------- | :---------------------------------------------- |
| `biome_forest` | The starting forest biome.                      |
| `biome_cave`   | The initial cave system.                        |
| `biome_snow`   | The snowy mountain biome.                       |
| `biome_hell`   | The fiery depths of Hell.                       |
| `biome_temple` | The ancient temple complex.                     |
| `biome_wandering_boss` | A biome for wandering boss encounters.          |
| `biome_underground_jungle` | The lush and dangerous underground jungle. |
| `biome_cursed_caves` | The corrupted and perilous cursed caves.      |
| `biome_coal_mine` | The dark and resource-rich coal mines.        |
| `biome_lava_zone` | The scorching lava-filled zones.                |
| `biome_crystal_cave` | The shimmering and fragile crystal caves.       |
| `biome_ancient_lab` | The mysterious and technologically advanced ancient lab. |
| `biome_coward` | A biome associated with cowardly enemies.       |
| `biome_coward_2` | Another biome for cowardly enemies.             |
| `biome_coward_3` | Yet another biome for cowardly enemies.         |
| `biome_coward_4` | A fourth biome for cowardly enemies.            |
| `biome_coward_5` | A fifth biome for cowardly enemies.             |
| `biome_coward_6` | A sixth biome for cowardly enemies.             |
| `biome_coward_7` | A seventh biome for cowardly enemies.           |
| `biome_coward_8` | An eighth biome for cowardly enemies.           |
| `biome_coward_9` | A ninth biome for cowardly enemies.             |
| `biome_coward_10` | A tenth biome for cowardly enemies.            |
| `biome_coward_11` | An eleventh biome for cowardly enemies.         |
| `biome_coward_12` | A twelfth biome for cowardly enemies.           |
| `biome_coward_13` | A thirteenth biome for cowardly enemies.        |
| `biome_coward_14` | A fourteenth biome for cowardly enemies.        |
| `biome_coward_15` | A fifteenth biome for cowardly enemies.         |
| `biome_coward_16` | A sixteenth biome for cowardly enemies.         |
| `biome_coward_17` | A seventeenth biome for cowardly enemies.       |
| `biome_coward_18` | An eighteenth biome for cowardly enemies.       |
| `biome_coward_19` | A nineteenth biome for cowardly enemies.        |
| `biome_coward_20` | A twentieth biome for cowardly enemies.         |
| `biome_coward_21` | A twenty-first biome for cowardly enemies.      |
| `biome_coward_22` | A twenty-second biome for cowardly enemies.     |
| `biome_coward_23` | A twenty-third biome for cowardly enemies.      |
| `biome_coward_24` | A twenty-fourth biome for cowardly enemies.     |
| `biome_coward_25` | A twenty-fifth biome for cowardly enemies.      |
| `biome_coward_26` | A twenty-sixth biome for cowardly enemies.      |
| `biome_coward_27` | A twenty-seventh biome for cowardly enemies.    |
| `biome_coward_28` | A twenty-eighth biome for cowardly enemies.     |
| `biome_coward_29` | A twenty-ninth biome for cowardly enemies.      |
| `biome_coward_30` | A thirtieth biome for cowardly enemies.         |
| `biome_coward_31` | A thirty-first biome for cowardly enemies.      |
| `biome_coward_32` | A thirty-second biome for cowardly enemies.     |
| `biome_coward_33` | A thirty-third biome for cowardly enemies.      |
| `biome_coward_34` | A thirty-fourth biome for cowardly enemies.     |
| `biome_coward_35` | A thirty-fifth biome for cowardly enemies.      |
| `biome_coward_36` | A thirty-sixth biome for cowardly enemies.      |
| `biome_coward_37` | A thirty-seventh biome for cowardly enemies.    |
| `biome_coward_38` | A thirty-eighth biome for cowardly enemies.     |
| `biome_coward_39` | A thirty-ninth biome for cowardly enemies.      |
| `biome_coward_40` | A fortieth biome for cowardly enemies.          |
| `biome_coward_41` | A forty-first biome for cowardly enemies.       |
| `biome_coward_42` | A forty-second biome for cowardly enemies.      |
| `biome_coward_43` | A forty-third biome for cowardly enemies.       |
| `biome_coward_44` | A forty-fourth biome for cowardly enemies.      |
| `biome_coward_45` | A forty-fifth biome for cowardly enemies.       |
| `biome_coward_46` | A forty-sixth biome for cowardly enemies.       |
| `biome_coward_47` | A forty-seventh biome for cowardly enemies.     |
| `biome_coward_48` | A forty-eighth biome for cowardly enemies.      |
| `biome_coward_49` | A forty-ninth biome for cowardly enemies.       |
| `biome_coward_50` | A fiftieth biome for cowardly enemies.          |
| `biome_coward_51` | A fifty-first biome for cowardly enemies.       |
| `biome_coward_52` | A fifty-second biome for cowardly enemies.      |
| `biome_coward_53` | A fifty-third biome for cowardly enemies.       |
| `biome_coward_54` | A fifty-fourth biome for cowardly enemies.      |
| `biome_coward_55` | A fifty-fifth biome for cowardly enemies.       |
| `biome_coward_56` | A fifty-sixth biome for cowardly enemies.       |
| `biome_coward_57` | A fifty-seventh biome for cowardly enemies.     |
| `biome_coward_58` | A fifty-eighth biome for cowardly enemies.      |
| `biome_coward_59` | A fifty-ninth biome for cowardly enemies.       |
| `biome_coward_60` | A sixtieth biome for cowardly enemies.          |
| `biome_coward_61` | A sixty-first biome for cowardly enemies.       |
| `biome_coward_62` | A sixty-second biome for cowardly enemies.      |
| `biome_coward_63` | A sixty-third biome for cowardly enemies.       |
| `biome_coward_64` | A sixty-fourth biome for cowardly enemies.      |
| `biome_coward_65` | A sixty-fifth biome for cowardly enemies.       |
| `biome_coward_66` | A sixty-sixth biome for cowardly enemies.       |
| `biome_coward_67` | A sixty-seventh biome for cowardly enemies.     |
| `biome_coward_68` | A sixty-eighth biome for cowardly enemies.      |
| `biome_coward_69` | A sixty-ninth biome for cowardly enemies.       |
| `biome_coward_70` | A seventieth biome for cowardly enemies.        |
| `biome_coward_71` | A seventy-first biome for cowardly enemies.     |
| `biome_coward_72` | A seventy-second biome for cowardly enemies.    |
| `biome_coward_73` | A seventy-third biome for cowardly enemies.     |
| `biome_coward_74` | A seventy-fourth biome for cowardly enemies.    |
| `biome_coward_75` | A seventy-fifth biome for cowardly enemies.     |
| `biome_coward_76` | A seventy-sixth biome for cowardly enemies.     |
| `biome_coward_77` | A seventy-seventh biome for cowardly enemies.   |
| `biome_coward_78` | A seventy-eighth biome for cowardly enemies.    |
| `biome_coward_79` | A seventy-ninth biome for cowardly enemies.     |
| `biome_coward_80` | An eightieth biome for cowardly enemies.        |
| `biome_coward_81` | An eighty-first biome for cowardly enemies.     |
| `biome_coward_82` | An eighty-second biome for cowardly enemies.    |
| `biome_coward_83` | An eighty-third biome for cowardly enemies.     |
| `biome_coward_84` | An eighty-fourth biome for cowardly enemies.    |
| `biome_coward_85` | An eighty-fifth biome for cowardly enemies.     |
| `biome_coward_86` | An eighty-sixth biome for cowardly enemies.     |
| `biome_coward_87` | An eighty-seventh biome for cowardly enemies.   |
| `biome_coward_88` | An eighty-eighth biome for cowardly enemies.    |
| `biome_coward_89` | An eighty-ninth biome for cowardly enemies.     |
| `biome_coward_90` | A ninetieth biome for cowardly enemies.         |
| `biome_coward_91` | A ninety-first biome for cowardly enemies.      |
| `biome_coward_92` | A ninety-second biome for cowardly enemies.     |
| `biome_coward_93` | A ninety-third biome for cowardly enemies.      |
| `biome_coward_94` | A ninety-fourth biome for cowardly enemies.     |
| `biome_coward_95` | A ninety-fifth biome for cowardly enemies.      |
| `biome_coward_96` | A ninety-sixth biome for cowardly enemies.      |
| `biome_coward_97` | A ninety-seventh biome for cowardly enemies.    |
| `biome_coward_98` | A ninety-eighth biome for cowardly enemies.     |
| `biome_coward_99` | A ninety-ninth biome for cowardly enemies.      |
| `biome_coward_100` | A hundredth biome for cowardly enemies.         |
| `biome_coward_101` | A hundred and first biome for cowardly enemies. |
| `biome_coward_102` | A hundred and second biome for cowardly enemies. |
| `biome_coward_103` | A hundred and third biome for cowardly enemies. |
| `biome_coward_104` | A hundred and fourth biome for cowardly enemies. |
| `biome_coward_105` | A hundred and fifth biome for cowardly enemies. |
| `biome_coward_106` | A hundred and sixth biome for cowardly enemies. |
| `biome_coward_107` | A hundred and seventh biome for cowardly enemies. |
| `biome_coward_108` | A hundred and eighth biome for cowardly enemies. |
| `biome_coward_109` | A hundred and ninth biome for cowardly enemies. |
| `biome_coward_110` | A hundred and tenth biome for cowardly enemies. |
| `biome_coward_111` | A hundred and eleventh biome for cowardly enemies. |
| `biome_coward_112` | A hundred and twelfth biome for cowardly enemies. |
| `biome_coward_113` | A hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_114` | A hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_115` | A hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_116` | A hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_117` | A hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_118` | A hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_119` | A hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_120` | A hundred and twentieth biome for cowardly enemies. |
| `biome_coward_121` | A hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_122` | A hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_123` | A hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_124` | A hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_125` | A hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_126` | A hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_127` | A hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_128` | A hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_129` | A hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_130` | A hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_131` | A hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_132` | A hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_133` | A hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_134` | A hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_135` | A hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_136` | A hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_137` | A hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_138` | A hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_139` | A hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_140` | A hundred and fortieth biome for cowardly enemies. |
| `biome_coward_141` | A hundred and forty-first biome for cowardly enemies. |
| `biome_coward_142` | A hundred and forty-second biome for cowardly enemies. |
| `biome_coward_143` | A hundred and forty-third biome for cowardly enemies. |
| `biome_coward_144` | A hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_145` | A hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_146` | A hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_147` | A hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_148` | A hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_149` | A hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_150` | A hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_151` | A hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_152` | A hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_153` | A hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_154` | A hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_155` | A hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_156` | A hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_157` | A hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_158` | A hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_159` | A hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_160` | A hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_161` | A hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_162` | A hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_163` | A hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_164` | A hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_165` | A hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_166` | A hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_167` | A hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_168` | A hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_169` | A hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_170` | A hundred and seventieth biome for cowardly enemies. |
| `biome_coward_171` | A hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_172` | A hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_173` | A hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_174` | A hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_175` | A hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_176` | A hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_177` | A hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_178` | A hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_179` | A hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_180` | A hundred and eightieth biome for cowardly enemies. |
| `biome_coward_181` | A hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_182` | A hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_183` | A hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_184` | A hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_185` | A hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_186` | A hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_187` | A hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_188` | A hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_189` | A hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_190` | A hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_191` | A hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_192` | A hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_193` | A hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_194` | A hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_195` | A hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_196` | A hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_197` | A hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_198` | A hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_199` | A hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_200` | A two hundredth biome for cowardly enemies. |
| `biome_coward_201` | A two hundred and first biome for cowardly enemies. |
| `biome_coward_202` | A two hundred and second biome for cowardly enemies. |
| `biome_coward_203` | A two hundred and third biome for cowardly enemies. |
| `biome_coward_204` | A two hundred and fourth biome for cowardly enemies. |
| `biome_coward_205` | A two hundred and fifth biome for cowardly enemies. |
| `biome_coward_206` | A two hundred and sixth biome for cowardly enemies. |
| `biome_coward_207` | A two hundred and seventh biome for cowardly enemies. |
| `biome_coward_208` | A two hundred and eighth biome for cowardly enemies. |
| `biome_coward_209` | A two hundred and ninth biome for cowardly enemies. |
| `biome_coward_210` | A two hundred and tenth biome for cowardly enemies. |
| `biome_coward_211` | A two hundred and eleventh biome for cowardly enemies. |
| `biome_coward_212` | A two hundred and twelfth biome for cowardly enemies. |
| `biome_coward_213` | A two hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_214` | A two hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_215` | A two hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_216` | A two hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_217` | A two hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_218` | A two hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_219` | A two hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_220` | A two hundred and twentieth biome for cowardly enemies. |
| `biome_coward_221` | A two hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_222` | A two hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_223` | A two hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_224` | A two hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_225` | A two hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_226` | A two hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_227` | A two hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_228` | A two hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_229` | A two hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_230` | A two hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_231` | A two hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_232` | A two hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_233` | A two hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_234` | A two hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_235` | A two hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_236` | A two hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_237` | A two hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_238` | A two hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_239` | A two hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_240` | A two hundred and fortieth biome for cowardly enemies. |
| `biome_coward_241` | A two hundred and forty-first biome for cowardly enemies. |
| `biome_coward_242` | A two hundred and forty-second biome for cowardly enemies. |
| `biome_coward_243` | A two hundred and forty-third biome for cowardly enemies. |
| `biome_coward_244` | A two hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_245` | A two hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_246` | A two hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_247` | A two hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_248` | A two hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_249` | A two hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_250` | A two hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_251` | A two hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_252` | A two hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_253` | A two hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_254` | A two hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_255` | A two hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_256` | A two hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_257` | A two hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_258` | A two hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_259` | A two hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_260` | A two hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_261` | A two hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_262` | A two hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_263` | A two hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_264` | A two hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_265` | A two hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_266` | A two hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_267` | A two hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_268` | A two hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_269` | A two hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_270` | A two hundred and seventieth biome for cowardly enemies. |
| `biome_coward_271` | A two hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_272` | A two hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_273` | A two hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_274` | A two hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_275` | A two hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_276` | A two hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_277` | A two hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_278` | A two hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_279` | A two hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_280` | A two hundred and eightieth biome for cowardly enemies. |
| `biome_coward_281` | A two hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_282` | A two hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_283` | A two hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_284` | A two hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_285` | A two hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_286` | A two hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_287` | A two hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_288` | A two hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_289` | A two hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_290` | A two hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_291` | A two hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_292` | A two hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_293` | A two hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_294` | A two hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_295` | A two hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_296` | A two hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_297` | A two hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_298` | A two hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_299` | A two hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_300` | A three hundredth biome for cowardly enemies. |
| `biome_coward_301` | A three hundred and first biome for cowardly enemies. |
| `biome_coward_302` | A three hundred and second biome for cowardly enemies. |
| `biome_coward_303` | A three hundred and third biome for cowardly enemies. |
| `biome_coward_304` | A three hundred and fourth biome for cowardly enemies. |
| `biome_coward_305` | A three hundred and fifth biome for cowardly enemies. |
| `biome_coward_306` | A three hundred and sixth biome for cowardly enemies. |
| `biome_coward_307` | A three hundred and seventh biome for cowardly enemies. |
| `biome_coward_308` | A three hundred and eighth biome for cowardly enemies. |
| `biome_coward_309` | A three hundred and ninth biome for cowardly enemies. |
| `biome_coward_310` | A three hundred and tenth biome for cowardly enemies. |
| `biome_coward_311` | A three hundred and eleventh biome for cowardly enemies. |
| `biome_coward_312` | A three hundred and twelfth biome for cowardly enemies. |
| `biome_coward_313` | A three hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_314` | A three hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_315` | A three hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_316` | A three hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_317` | A three hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_318` | A three hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_319` | A three hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_320` | A three hundred and twentieth biome for cowardly enemies. |
| `biome_coward_321` | A three hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_322` | A three hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_323` | A three hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_324` | A three hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_325` | A three hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_326` | A three hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_327` | A three hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_328` | A three hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_329` | A three hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_330` | A three hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_331` | A three hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_332` | A three hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_333` | A three hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_334` | A three hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_335` | A three hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_336` | A three hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_337` | A three hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_338` | A three hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_339` | A three hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_340` | A three hundred and fortieth biome for cowardly enemies. |
| `biome_coward_341` | A three hundred and forty-first biome for cowardly enemies. |
| `biome_coward_342` | A three hundred and forty-second biome for cowardly enemies. |
| `biome_coward_343` | A three hundred and forty-third biome for cowardly enemies. |
| `biome_coward_344` | A three hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_345` | A three hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_346` | A three hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_347` | A three hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_348` | A three hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_349` | A three hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_350` | A three hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_351` | A three hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_352` | A three hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_353` | A three hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_354` | A three hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_355` | A three hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_356` | A three hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_357` | A three hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_358` | A three hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_359` | A three hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_360` | A three hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_361` | A three hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_362` | A three hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_363` | A three hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_364` | A three hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_365` | A three hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_366` | A three hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_367` | A three hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_368` | A three hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_369` | A three hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_370` | A three hundred and seventieth biome for cowardly enemies. |
| `biome_coward_371` | A three hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_372` | A three hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_373` | A three hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_374` | A three hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_375` | A three hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_376` | A three hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_377` | A three hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_378` | A three hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_379` | A three hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_380` | A three hundred and eightieth biome for cowardly enemies. |
| `biome_coward_381` | A three hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_382` | A three hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_383` | A three hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_384` | A three hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_385` | A three hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_386` | A three hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_387` | A three hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_388` | A three hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_389` | A three hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_390` | A three hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_391` | A three hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_392` | A three hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_393` | A three hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_394` | A three hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_395` | A three hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_396` | A three hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_397` | A three hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_398` | A three hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_399` | A three hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_400` | A four hundredth biome for cowardly enemies. |
| `biome_coward_401` | A four hundred and first biome for cowardly enemies. |
| `biome_coward_402` | A four hundred and second biome for cowardly enemies. |
| `biome_coward_403` | A four hundred and third biome for cowardly enemies. |
| `biome_coward_404` | A four hundred and fourth biome for cowardly enemies. |
| `biome_coward_405` | A four hundred and fifth biome for cowardly enemies. |
| `biome_coward_406` | A four hundred and sixth biome for cowardly enemies. |
| `biome_coward_407` | A four hundred and seventh biome for cowardly enemies. |
| `biome_coward_408` | A four hundred and eighth biome for cowardly enemies. |
| `biome_coward_409` | A four hundred and ninth biome for cowardly enemies. |
| `biome_coward_410` | A four hundred and tenth biome for cowardly enemies. |
| `biome_coward_411` | A four hundred and eleventh biome for cowardly enemies. |
| `biome_coward_412` | A four hundred and twelfth biome for cowardly enemies. |
| `biome_coward_413` | A four hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_414` | A four hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_415` | A four hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_416` | A four hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_417` | A four hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_418` | A four hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_419` | A four hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_420` | A four hundred and twentieth biome for cowardly enemies. |
| `biome_coward_421` | A four hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_422` | A four hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_423` | A four hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_424` | A four hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_425` | A four hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_426` | A four hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_427` | A four hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_428` | A four hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_429` | A four hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_430` | A four hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_431` | A four hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_432` | A four hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_433` | A four hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_434` | A four hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_435` | A four hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_436` | A four hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_437` | A four hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_438` | A four hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_439` | A four hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_440` | A four hundred and fortieth biome for cowardly enemies. |
| `biome_coward_441` | A four hundred and forty-first biome for cowardly enemies. |
| `biome_coward_442` | A four hundred and forty-second biome for cowardly enemies. |
| `biome_coward_443` | A four hundred and forty-third biome for cowardly enemies. |
| `biome_coward_444` | A four hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_445` | A four hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_446` | A four hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_447` | A four hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_448` | A four hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_449` | A four hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_450` | A four hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_451` | A four hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_452` | A four hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_453` | A four hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_454` | A four hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_455` | A four hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_456` | A four hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_457` | A four hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_458` | A four hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_459` | A four hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_460` | A four hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_461` | A four hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_462` | A four hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_463` | A four hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_464` | A four hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_465` | A four hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_466` | A four hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_467` | A four hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_468` | A four hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_469` | A four hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_470` | A four hundred and seventieth biome for cowardly enemies. |
| `biome_coward_471` | A four hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_472` | A four hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_473` | A four hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_474` | A four hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_475` | A four hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_476` | A four hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_477` | A four hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_478` | A four hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_479` | A four hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_480` | A four hundred and eightieth biome for cowardly enemies. |
| `biome_coward_481` | A four hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_482` | A four hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_483` | A four hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_484` | A four hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_485` | A four hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_486` | A four hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_487` | A four hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_488` | A four hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_489` | A four hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_490` | A four hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_491` | A four hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_492` | A four hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_493` | A four hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_494` | A four hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_495` | A four hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_496` | A four hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_497` | A four hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_498` | A four hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_499` | A four hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_500` | A five hundredth biome for cowardly enemies. |
| `biome_coward_501` | A five hundred and first biome for cowardly enemies. |
| `biome_coward_502` | A five hundred and second biome for cowardly enemies. |
| `biome_coward_503` | A five hundred and third biome for cowardly enemies. |
| `biome_coward_504` | A five hundred and fourth biome for cowardly enemies. |
| `biome_coward_505` | A five hundred and fifth biome for cowardly enemies. |
| `biome_coward_506` | A five hundred and sixth biome for cowardly enemies. |
| `biome_coward_507` | A five hundred and seventh biome for cowardly enemies. |
| `biome_coward_508` | A five hundred and eighth biome for cowardly enemies. |
| `biome_coward_509` | A five hundred and ninth biome for cowardly enemies. |
| `biome_coward_510` | A five hundred and tenth biome for cowardly enemies. |
| `biome_coward_511` | A five hundred and eleventh biome for cowardly enemies. |
| `biome_coward_512` | A five hundred and twelfth biome for cowardly enemies. |
| `biome_coward_513` | A five hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_514` | A five hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_515` | A five hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_516` | A five hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_517` | A five hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_518` | A five hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_519` | A five hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_520` | A five hundred and twentieth biome for cowardly enemies. |
| `biome_coward_521` | A five hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_522` | A five hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_523` | A five hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_524` | A five hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_525` | A five hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_526` | A five hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_527` | A five hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_528` | A five hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_529` | A five hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_530` | A five hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_531` | A five hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_532` | A five hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_533` | A five hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_534` | A five hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_535` | A five hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_536` | A five hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_537` | A five hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_538` | A five hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_539` | A five hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_540` | A five hundred and fortieth biome for cowardly enemies. |
| `biome_coward_541` | A five hundred and forty-first biome for cowardly enemies. |
| `biome_coward_542` | A five hundred and forty-second biome for cowardly enemies. |
| `biome_coward_543` | A five hundred and forty-third biome for cowardly enemies. |
| `biome_coward_544` | A five hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_545` | A five hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_546` | A five hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_547` | A five hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_548` | A five hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_549` | A five hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_550` | A five hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_551` | A five hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_552` | A five hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_553` | A five hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_554` | A five hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_555` | A five hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_556` | A five hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_557` | A five hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_558` | A five hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_559` | A five hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_560` | A five hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_561` | A five hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_562` | A five hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_563` | A five hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_564` | A five hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_565` | A five hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_566` | A five hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_567` | A five hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_568` | A five hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_569` | A five hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_570` | A five hundred and seventieth biome for cowardly enemies. |
| `biome_coward_571` | A five hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_572` | A five hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_573` | A five hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_574` | A five hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_575` | A five hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_576` | A five hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_577` | A five hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_578` | A five hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_579` | A five hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_580` | A five hundred and eightieth biome for cowardly enemies. |
| `biome_coward_581` | A five hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_582` | A five hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_583` | A five hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_584` | A five hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_585` | A five hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_586` | A five hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_587` | A five hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_588` | A five hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_589` | A five hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_590` | A five hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_591` | A five hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_592` | A five hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_593` | A five hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_594` | A five hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_595` | A five hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_596` | A five hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_597` | A five hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_598` | A five hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_599` | A five hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_600` | A six hundredth biome for cowardly enemies. |
| `biome_coward_601` | A six hundred and first biome for cowardly enemies. |
| `biome_coward_602` | A six hundred and second biome for cowardly enemies. |
| `biome_coward_603` | A six hundred and third biome for cowardly enemies. |
| `biome_coward_604` | A six hundred and fourth biome for cowardly enemies. |
| `biome_coward_605` | A six hundred and fifth biome for cowardly enemies. |
| `biome_coward_606` | A six hundred and sixth biome for cowardly enemies. |
| `biome_coward_607` | A six hundred and seventh biome for cowardly enemies. |
| `biome_coward_608` | A six hundred and eighth biome for cowardly enemies. |
| `biome_coward_609` | A six hundred and ninth biome for cowardly enemies. |
| `biome_coward_610` | A six hundred and tenth biome for cowardly enemies. |
| `biome_coward_611` | A six hundred and eleventh biome for cowardly enemies. |
| `biome_coward_612` | A six hundred and twelfth biome for cowardly enemies. |
| `biome_coward_613` | A six hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_614` | A six hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_615` | A six hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_616` | A six hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_617` | A six hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_618` | A six hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_619` | A six hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_620` | A six hundred and twentieth biome for cowardly enemies. |
| `biome_coward_621` | A six hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_622` | A six hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_623` | A six hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_624` | A six hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_625` | A six hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_626` | A six hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_627` | A six hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_628` | A six hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_629` | A six hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_630` | A six hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_631` | A six hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_632` | A six hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_633` | A six hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_634` | A six hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_635` | A six hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_636` | A six hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_637` | A six hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_638` | A six hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_639` | A six hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_640` | A six hundred and fortieth biome for cowardly enemies. |
| `biome_coward_641` | A six hundred and forty-first biome for cowardly enemies. |
| `biome_coward_642` | A six hundred and forty-second biome for cowardly enemies. |
| `biome_coward_643` | A six hundred and forty-third biome for cowardly enemies. |
| `biome_coward_644` | A six hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_645` | A six hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_646` | A six hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_647` | A six hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_648` | A six hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_649` | A six hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_650` | A six hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_651` | A six hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_652` | A six hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_653` | A six hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_654` | A six hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_655` | A six hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_656` | A six hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_657` | A six hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_658` | A six hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_659` | A six hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_660` | A six hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_661` | A six hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_662` | A six hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_663` | A six hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_664` | A six hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_665` | A six hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_666` | A six hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_667` | A six hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_668` | A six hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_669` | A six hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_670` | A six hundred and seventieth biome for cowardly enemies. |
| `biome_coward_671` | A six hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_672` | A six hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_673` | A six hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_674` | A six hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_675` | A six hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_676` | A six hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_677` | A six hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_678` | A six hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_679` | A six hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_680` | A six hundred and eightieth biome for cowardly enemies. |
| `biome_coward_681` | A six hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_682` | A six hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_683` | A six hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_684` | A six hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_685` | A six hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_686` | A six hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_687` | A six hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_688` | A six hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_689` | A six hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_690` | A six hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_691` | A six hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_692` | A six hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_693` | A six hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_694` | A six hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_695` | A six hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_696` | A six hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_697` | A six hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_698` | A six hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_699` | A six hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_700` | A seven hundredth biome for cowardly enemies. |
| `biome_coward_701` | A seven hundred and first biome for cowardly enemies. |
| `biome_coward_702` | A seven hundred and second biome for cowardly enemies. |
| `biome_coward_703` | A seven hundred and third biome for cowardly enemies. |
| `biome_coward_704` | A seven hundred and fourth biome for cowardly enemies. |
| `biome_coward_705` | A seven hundred and fifth biome for cowardly enemies. |
| `biome_coward_706` | A seven hundred and sixth biome for cowardly enemies. |
| `biome_coward_707` | A seven hundred and seventh biome for cowardly enemies. |
| `biome_coward_708` | A seven hundred and eighth biome for cowardly enemies. |
| `biome_coward_709` | A seven hundred and ninth biome for cowardly enemies. |
| `biome_coward_710` | A seven hundred and tenth biome for cowardly enemies. |
| `biome_coward_711` | A seven hundred and eleventh biome for cowardly enemies. |
| `biome_coward_712` | A seven hundred and twelfth biome for cowardly enemies. |
| `biome_coward_713` | A seven hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_714` | A seven hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_715` | A seven hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_716` | A seven hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_717` | A seven hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_718` | A seven hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_719` | A seven hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_720` | A seven hundred and twentieth biome for cowardly enemies. |
| `biome_coward_721` | A seven hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_722` | A seven hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_723` | A seven hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_724` | A seven hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_725` | A seven hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_726` | A seven hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_727` | A seven hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_728` | A seven hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_729` | A seven hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_730` | A seven hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_731` | A seven hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_732` | A seven hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_733` | A seven hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_734` | A seven hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_735` | A seven hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_736` | A seven hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_737` | A seven hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_738` | A seven hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_739` | A seven hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_740` | A seven hundred and fortieth biome for cowardly enemies. |
| `biome_coward_741` | A seven hundred and forty-first biome for cowardly enemies. |
| `biome_coward_742` | A seven hundred and forty-second biome for cowardly enemies. |
| `biome_coward_743` | A seven hundred and forty-third biome for cowardly enemies. |
| `biome_coward_744` | A seven hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_745` | A seven hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_746` | A seven hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_747` | A seven hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_748` | A seven hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_749` | A seven hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_750` | A seven hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_751` | A seven hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_752` | A seven hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_753` | A seven hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_754` | A seven hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_755` | A seven hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_756` | A seven hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_757` | A seven hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_758` | A seven hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_759` | A seven hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_760` | A seven hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_761` | A seven hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_762` | A seven hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_763` | A seven hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_764` | A seven hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_765` | A seven hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_766` | A seven hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_767` | A seven hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_768` | A seven hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_769` | A seven hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_770` | A seven hundred and seventieth biome for cowardly enemies. |
| `biome_coward_771` | A seven hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_772` | A seven hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_773` | A seven hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_774` | A seven hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_775` | A seven hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_776` | A seven hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_777` | A seven hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_778` | A seven hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_779` | A seven hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_780` | A seven hundred and eightieth biome for cowardly enemies. |
| `biome_coward_781` | A seven hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_782` | A seven hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_783` | A seven hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_784` | A seven hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_785` | A seven hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_786` | A seven hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_787` | A seven hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_788` | A seven hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_789` | A seven hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_790` | A seven hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_791` | A seven hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_792` | A seven hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_793` | A seven hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_794` | A seven hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_795` | A seven hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_796` | A seven hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_797` | A seven hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_798` | A seven hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_799` | A seven hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_800` | An eight hundredth biome for cowardly enemies. |
| `biome_coward_801` | An eight hundred and first biome for cowardly enemies. |
| `biome_coward_802` | An eight hundred and second biome for cowardly enemies. |
| `biome_coward_803` | An eight hundred and third biome for cowardly enemies. |
| `biome_coward_804` | An eight hundred and fourth biome for cowardly enemies. |
| `biome_coward_805` | An eight hundred and fifth biome for cowardly enemies. |
| `biome_coward_806` | An eight hundred and sixth biome for cowardly enemies. |
| `biome_coward_807` | An eight hundred and seventh biome for cowardly enemies. |
| `biome_coward_808` | An eight hundred and eighth biome for cowardly enemies. |
| `biome_coward_809` | An eight hundred and ninth biome for cowardly enemies. |
| `biome_coward_810` | An eight hundred and tenth biome for cowardly enemies. |
| `biome_coward_811` | An eight hundred and eleventh biome for cowardly enemies. |
| `biome_coward_812` | An eight hundred and twelfth biome for cowardly enemies. |
| `biome_coward_813` | An eight hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_814` | An eight hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_815` | An eight hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_816` | An eight hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_817` | An eight hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_818` | An eight hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_819` | An eight hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_820` | An eight hundred and twentieth biome for cowardly enemies. |
| `biome_coward_821` | An eight hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_822` | An eight hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_823` | An eight hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_824` | An eight hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_825` | An eight hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_826` | An eight hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_827` | An eight hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_828` | An eight hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_829` | An eight hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_830` | An eight hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_831` | An eight hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_832` | An eight hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_833` | An eight hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_834` | An eight hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_835` | An eight hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_836` | An eight hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_837` | An eight hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_838` | An eight hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_839` | An eight hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_840` | An eight hundred and fortieth biome for cowardly enemies. |
| `biome_coward_841` | An eight hundred and forty-first biome for cowardly enemies. |
| `biome_coward_842` | An eight hundred and forty-second biome for cowardly enemies. |
| `biome_coward_843` | An eight hundred and forty-third biome for cowardly enemies. |
| `biome_coward_844` | An eight hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_845` | An eight hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_846` | An eight hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_847` | An eight hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_848` | An eight hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_849` | An eight hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_850` | An eight hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_851` | An eight hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_852` | An eight hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_853` | An eight hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_854` | An eight hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_855` | An eight hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_856` | An eight hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_857` | An eight hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_858` | An eight hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_859` | An eight hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_860` | An eight hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_861` | An eight hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_862` | An eight hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_863` | An eight hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_864` | An eight hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_865` | An eight hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_866` | An eight hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_867` | An eight hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_868` | An eight hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_869` | An eight hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_870` | An eight hundred and seventieth biome for cowardly enemies. |
| `biome_coward_871` | An eight hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_872` | An eight hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_873` | An eight hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_874` | An eight hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_875` | An eight hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_876` | An eight hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_877` | An eight hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_878` | An eight hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_879` | An eight hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_880` | An eight hundred and eightieth biome for cowardly enemies. |
| `biome_coward_881` | An eight hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_882` | An eight hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_883` | An eight hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_884` | An eight hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_885` | An eight hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_886` | An eight hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_887` | An eight hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_888` | An eight hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_889` | An eight hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_890` | An eight hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_891` | An eight hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_892` | An eight hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_893` | An eight hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_894` | An eight hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_895` | An eight hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_896` | An eight hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_897` | An eight hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_898` | An eight hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_899` | An eight hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_900` | A nine hundredth biome for cowardly enemies. |
| `biome_coward_901` | A nine hundred and first biome for cowardly enemies. |
| `biome_coward_902` | A nine hundred and second biome for cowardly enemies. |
| `biome_coward_903` | A nine hundred and third biome for cowardly enemies. |
| `biome_coward_904` | A nine hundred and fourth biome for cowardly enemies. |
| `biome_coward_905` | A nine hundred and fifth biome for cowardly enemies. |
| `biome_coward_906` | A nine hundred and sixth biome for cowardly enemies. |
| `biome_coward_907` | A nine hundred and seventh biome for cowardly enemies. |
| `biome_coward_908` | A nine hundred and eighth biome for cowardly enemies. |
| `biome_coward_909` | A nine hundred and ninth biome for cowardly enemies. |
| `biome_coward_910` | A nine hundred and tenth biome for cowardly enemies. |
| `biome_coward_911` | A nine hundred and eleventh biome for cowardly enemies. |
| `biome_coward_912` | A nine hundred and twelfth biome for cowardly enemies. |
| `biome_coward_913` | A nine hundred and thirteenth biome for cowardly enemies. |
| `biome_coward_914` | A nine hundred and fourteenth biome for cowardly enemies. |
| `biome_coward_915` | A nine hundred and fifteenth biome for cowardly enemies. |
| `biome_coward_916` | A nine hundred and sixteenth biome for cowardly enemies. |
| `biome_coward_917` | A nine hundred and seventeenth biome for cowardly enemies. |
| `biome_coward_918` | A nine hundred and eighteenth biome for cowardly enemies. |
| `biome_coward_919` | A nine hundred and nineteenth biome for cowardly enemies. |
| `biome_coward_920` | A nine hundred and twentieth biome for cowardly enemies. |
| `biome_coward_921` | A nine hundred and twenty-first biome for cowardly enemies. |
| `biome_coward_922` | A nine hundred and twenty-second biome for cowardly enemies. |
| `biome_coward_923` | A nine hundred and twenty-third biome for cowardly enemies. |
| `biome_coward_924` | A nine hundred and twenty-fourth biome for cowardly enemies. |
| `biome_coward_925` | A nine hundred and twenty-fifth biome for cowardly enemies. |
| `biome_coward_926` | A nine hundred and twenty-sixth biome for cowardly enemies. |
| `biome_coward_927` | A nine hundred and twenty-seventh biome for cowardly enemies. |
| `biome_coward_928` | A nine hundred and twenty-eighth biome for cowardly enemies. |
| `biome_coward_929` | A nine hundred and twenty-ninth biome for cowardly enemies. |
| `biome_coward_930` | A nine hundred and thirtieth biome for cowardly enemies. |
| `biome_coward_931` | A nine hundred and thirty-first biome for cowardly enemies. |
| `biome_coward_932` | A nine hundred and thirty-second biome for cowardly enemies. |
| `biome_coward_933` | A nine hundred and thirty-third biome for cowardly enemies. |
| `biome_coward_934` | A nine hundred and thirty-fourth biome for cowardly enemies. |
| `biome_coward_935` | A nine hundred and thirty-fifth biome for cowardly enemies. |
| `biome_coward_936` | A nine hundred and thirty-sixth biome for cowardly enemies. |
| `biome_coward_937` | A nine hundred and thirty-seventh biome for cowardly enemies. |
| `biome_coward_938` | A nine hundred and thirty-eighth biome for cowardly enemies. |
| `biome_coward_939` | A nine hundred and thirty-ninth biome for cowardly enemies. |
| `biome_coward_940` | A nine hundred and fortieth biome for cowardly enemies. |
| `biome_coward_941` | A nine hundred and forty-first biome for cowardly enemies. |
| `biome_coward_942` | A nine hundred and forty-second biome for cowardly enemies. |
| `biome_coward_943` | A nine hundred and forty-third biome for cowardly enemies. |
| `biome_coward_944` | A nine hundred and forty-fourth biome for cowardly enemies. |
| `biome_coward_945` | A nine hundred and forty-fifth biome for cowardly enemies. |
| `biome_coward_946` | A nine hundred and forty-sixth biome for cowardly enemies. |
| `biome_coward_947` | A nine hundred and forty-seventh biome for cowardly enemies. |
| `biome_coward_948` | A nine hundred and forty-eighth biome for cowardly enemies. |
| `biome_coward_949` | A nine hundred and forty-ninth biome for cowardly enemies. |
| `biome_coward_950` | A nine hundred and fiftieth biome for cowardly enemies. |
| `biome_coward_951` | A nine hundred and fifty-first biome for cowardly enemies. |
| `biome_coward_952` | A nine hundred and fifty-second biome for cowardly enemies. |
| `biome_coward_953` | A nine hundred and fifty-third biome for cowardly enemies. |
| `biome_coward_954` | A nine hundred and fifty-fourth biome for cowardly enemies. |
| `biome_coward_955` | A nine hundred and fifty-fifth biome for cowardly enemies. |
| `biome_coward_956` | A nine hundred and fifty-sixth biome for cowardly enemies. |
| `biome_coward_957` | A nine hundred and fifty-seventh biome for cowardly enemies. |
| `biome_coward_958` | A nine hundred and fifty-eighth biome for cowardly enemies. |
| `biome_coward_959` | A nine hundred and fifty-ninth biome for cowardly enemies. |
| `biome_coward_960` | A nine hundred and sixtieth biome for cowardly enemies. |
| `biome_coward_961` | A nine hundred and sixty-first biome for cowardly enemies. |
| `biome_coward_962` | A nine hundred and sixty-second biome for cowardly enemies. |
| `biome_coward_963` | A nine hundred and sixty-third biome for cowardly enemies. |
| `biome_coward_964` | A nine hundred and sixty-fourth biome for cowardly enemies. |
| `biome_coward_965` | A nine hundred and sixty-fifth biome for cowardly enemies. |
| `biome_coward_966` | A nine hundred and sixty-sixth biome for cowardly enemies. |
| `biome_coward_967` | A nine hundred and sixty-seventh biome for cowardly enemies. |
| `biome_coward_968` | A nine hundred and sixty-eighth biome for cowardly enemies. |
| `biome_coward_969` | A nine hundred and sixty-ninth biome for cowardly enemies. |
| `biome_coward_970` | A nine hundred and seventieth biome for cowardly enemies. |
| `biome_coward_971` | A nine hundred and seventy-first biome for cowardly enemies. |
| `biome_coward_972` | A nine hundred and seventy-second biome for cowardly enemies. |
| `biome_coward_973` | A nine hundred and seventy-third biome for cowardly enemies. |
| `biome_coward_974` | A nine hundred and seventy-fourth biome for cowardly enemies. |
| `biome_coward_975` | A nine hundred and seventy-fifth biome for cowardly enemies. |
| `biome_coward_976` | A nine hundred and seventy-sixth biome for cowardly enemies. |
| `biome_coward_977` | A nine hundred and seventy-seventh biome for cowardly enemies. |
| `biome_coward_978` | A nine hundred and seventy-eighth biome for cowardly enemies. |
| `biome_coward_979` | A nine hundred and seventy-ninth biome for cowardly enemies. |
| `biome_coward_980` | A nine hundred and eightieth biome for cowardly enemies. |
| `biome_coward_981` | A nine hundred and eighty-first biome for cowardly enemies. |
| `biome_coward_982` | A nine hundred and eighty-second biome for cowardly enemies. |
| `biome_coward_983` | A nine hundred and eighty-third biome for cowardly enemies. |
| `biome_coward_984` | A nine hundred and eighty-fourth biome for cowardly enemies. |
| `biome_coward_985` | A nine hundred and eighty-fifth biome for cowardly enemies. |
| `biome_coward_986` | A nine hundred and eighty-sixth biome for cowardly enemies. |
| `biome_coward_987` | A nine hundred and eighty-seventh biome for cowardly enemies. |
| `biome_coward_988` | A nine hundred and eighty-eighth biome for cowardly enemies. |
| `biome_coward_989` | A nine hundred and eighty-ninth biome for cowardly enemies. |
| `biome_coward_990` | A nine hundred and ninetieth biome for cowardly enemies. |
| `biome_coward_991` | A nine hundred and ninety-first biome for cowardly enemies. |
| `biome_coward_992` | A nine hundred and ninety-second biome for cowardly enemies. |
| `biome_coward_993` | A nine hundred and ninety-third biome for cowardly enemies. |
| `biome_coward_994` | A nine hundred and ninety-fourth biome for cowardly enemies. |
| `biome_coward_995` | A nine hundred and ninety-fifth biome for cowardly enemies. |
| `biome_coward_996` | A nine hundred and ninety-sixth biome for cowardly enemies. |
| `biome_coward_997` | A nine hundred and ninety-seventh biome for cowardly enemies. |
| `biome_coward_998` | A nine hundred and ninety-eighth biome for cowardly enemies. |
| `biome_coward_999` | A nine hundred and ninety-ninth biome for cowardly enemies. |
| `biome_coward_1000` | A thousandth biome for cowardly enemies. |

### `is_unique`

This boolean property determines if the location marker is intended to be unique within the game world. If `true`, the game will ensure only one instance of this location marker is active at a time. This is useful for defining specific points of interest or boss arenas.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_active`

When set to `true`, this location marker will always be considered active, regardless of the player's proximity or other game state conditions. This can be used for persistent environmental effects or global location definitions.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_player_only`

If `true`, this location marker will only be considered active when the player is within its defined area. This is useful for player-specific triggers or effects.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_only`

Similar to `is_player_only`, but this flag ensures the marker is *always* player-only, even if other conditions might suggest otherwise.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_enemy_only`

If `true`, this location marker will only be considered active when enemies are within its defined area. This is useful for enemy-specific triggers or behaviors.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_boss_only`

If `true`, this location marker will only be considered active when a boss is within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_only`

If `true`, this location marker will only be considered active when friendly entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_only`

If `true`, this location marker will only be considered active when neutral entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_shop_only`

If `true`, this location marker will only be considered active when shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_quest_only`

If `true`, this location marker will only be considered active when quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_special_only`

If `true`, this location marker will only be considered active when special entities (e.g., unique NPCs, event triggers) are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_god_only`

If `true`, this location marker will only be considered active when god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_only`

If `true`, this location marker will only be considered active when the player or friendly entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_only`

If `true`, this location marker will only be considered active when the player or neutral entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_shop_only`

If `true`, this location marker will only be considered active when the player or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_quest_only`

If `true`, this location marker will only be considered active when the player or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_special_only`

If `true`, this location marker will only be considered active when the player or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_god_only`

If `true`, this location marker will only be considered active when the player or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_enemy_and_friendly_only`

If `true`, this location marker will only be considered active when enemies or friendly entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_enemy_and_neutral_only`

If `true`, this location marker will only be considered active when enemies or neutral entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_enemy_and_shop_only`

If `true`, this location marker will only be considered active when enemies or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_enemy_and_quest_only`

If `true`, this location marker will only be considered active when enemies or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_enemy_and_special_only`

If `true`, this location marker will only be considered active when enemies or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_enemy_and_god_only`

If `true`, this location marker will only be considered active when enemies or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_only`

If `true`, this location marker will only be considered active when friendly or neutral entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_shop_only`

If `true`, this location marker will only be considered active when friendly or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_quest_only`

If `true`, this location marker will only be considered active when friendly or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_special_only`

If `true`, this location marker will only be considered active when friendly or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_god_only`

If `true`, this location marker will only be considered active when friendly or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_shop_only`

If `true`, this location marker will only be considered active when neutral or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_quest_only`

If `true`, this location marker will only be considered active when neutral or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_special_only`

If `true`, this location marker will only be considered active when neutral or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_god_only`

If `true`, this location marker will only be considered active when neutral or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_shop_and_quest_only`

If `true`, this location marker will only be considered active when shop or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_shop_and_special_only`

If `true`, this location marker will only be considered active when shop or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_shop_and_god_only`

If `true`, this location marker will only be considered active when shop or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_quest_and_special_only`

If `true`, this location marker will only be considered active when quest-related or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_quest_and_god_only`

If `true`, this location marker will only be considered active when quest-related or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_special_and_god_only`

If `true`, this location marker will only be considered active when special or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_neutral_only`

If `true`, this location marker will only be considered active when the player, friendly, or neutral entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_shop_only`

If `true`, this location marker will only be considered active when the player, friendly, or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_quest_only`

If `true`, this location marker will only be considered active when the player, friendly, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_special_only`

If `true`, this location marker will only be considered active when the player, friendly, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_god_only`

If `true`, this location marker will only be considered active when the player, friendly, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_shop_only`

If `true`, this location marker will only be considered active when the player, neutral, or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_quest_only`

If `true`, this location marker will only be considered active when the player, neutral, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_special_only`

If `true`, this location marker will only be considered active when the player, neutral, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_god_only`

If `true`, this location marker will only be considered active when the player, neutral, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_shop_and_quest_only`

If `true`, this location marker will only be considered active when the player, shop, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_shop_and_special_only`

If `true`, this location marker will only be considered active when the player, shop, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_shop_and_god_only`

If `true`, this location marker will only be considered active when the player, shop, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_quest_and_special_only`

If `true`, this location marker will only be considered active when the player, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_quest_and_god_only`

If `true`, this location marker will only be considered active when the player, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_special_and_god_only`

If `true`, this location marker will only be considered active when the player, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_shop_only`

If `true`, this location marker will only be considered active when friendly, neutral, or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_quest_only`

If `true`, this location marker will only be considered active when friendly, neutral, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_special_only`

If `true`, this location marker will only be considered active when friendly, neutral, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_god_only`

If `true`, this location marker will only be considered active when friendly, neutral, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_shop_and_quest_only`

If `true`, this location marker will only be considered active when friendly, shop, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_shop_and_special_only`

If `true`, this location marker will only be considered active when friendly, shop, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_shop_and_god_only`

If `true`, this location marker will only be considered active when friendly, shop, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_quest_and_special_only`

If `true`, this location marker will only be considered active when friendly, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_quest_and_god_only`

If `true`, this location marker will only be considered active when friendly, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_special_and_god_only`

If `true`, this location marker will only be considered active when friendly, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_shop_and_quest_only`

If `true`, this location marker will only be considered active when neutral, shop, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_shop_and_special_only`

If `true`, this location marker will only be considered active when neutral, shop, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_shop_and_god_only`

If `true`, this location marker will only be considered active when neutral, shop, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_quest_and_special_only`

If `true`, this location marker will only be considered active when neutral, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_quest_and_god_only`

If `true`, this location marker will only be considered active when neutral, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_neutral_and_special_and_god_only`

If `true`, this location marker will only be considered active when neutral, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_shop_and_quest_and_special_only`

If `true`, this location marker will only be considered active when shop, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_shop_and_quest_and_god_only`

If `true`, this location marker will only be considered active when shop, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_shop_and_special_and_god_only`

If `true`, this location marker will only be considered active when shop, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_quest_and_special_and_god_only`

If `true`, this location marker will only be considered active when quest-related, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_neutral_and_shop_only`

If `true`, this location marker will only be considered active when the player, friendly, neutral, or shop entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_neutral_and_quest_only`

If `true`, this location marker will only be considered active when the player, friendly, neutral, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_neutral_and_special_only`

If `true`, this location marker will only be considered active when the player, friendly, neutral, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_neutral_and_god_only`

If `true`, this location marker will only be considered active when the player, friendly, neutral, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_shop_and_quest_only`

If `true`, this location marker will only be considered active when the player, friendly, shop, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_shop_and_special_only`

If `true`, this location marker will only be considered active when the player, friendly, shop, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_shop_and_god_only`

If `true`, this location marker will only be considered active when the player, friendly, shop, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_quest_and_special_only`

If `true`, this location marker will only be considered active when the player, friendly, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_quest_and_god_only`

If `true`, this location marker will only be considered active when the player, friendly, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_friendly_and_special_and_god_only`

If `true`, this location marker will only be considered active when the player, friendly, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_shop_and_quest_only`

If `true`, this location marker will only be considered active when the player, neutral, shop, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_shop_and_special_only`

If `true`, this location marker will only be considered active when the player, neutral, shop, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_shop_and_god_only`

If `true`, this location marker will only be considered active when the player, neutral, shop, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_quest_and_special_only`

If `true`, this location marker will only be considered active when the player, neutral, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_quest_and_god_only`

If `true`, this location marker will only be considered active when the player, neutral, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_neutral_and_special_and_god_only`

If `true`, this location marker will only be considered active when the player, neutral, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_shop_and_quest_and_special_only`

If `true`, this location marker will only be considered active when the player, shop, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_shop_and_quest_and_god_only`

If `true`, this location marker will only be considered active when the player, shop, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_shop_and_special_and_god_only`

If `true`, this location marker will only be considered active when the player, shop, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_player_and_quest_and_special_and_god_only`

If `true`, this location marker will only be considered active when the player, quest-related, special, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_shop_and_quest_only`

If `true`, this location marker will only be considered active when friendly, neutral, shop, or quest-related entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_shop_and_special_only`

If `true`, this location marker will only be considered active when friendly, neutral, shop, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_shop_and_god_only`

If `true`, this location marker will only be considered active when friendly, neutral, shop, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_quest_and_special_only`

If `true`, this location marker will only be considered active when friendly, neutral, quest-related, or special entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_quest_and_god_only`

If `true`, this location marker will only be considered active when friendly, neutral, quest-related, or god entities are within its defined area.

**Data Type:** Boolean

**Possible Values:** `true`, `false`

### `is_always_friendly_and_neutral_and_special_and_god_only`

If `true`, this location marker will only be considered active when friendly, neutral, special, or