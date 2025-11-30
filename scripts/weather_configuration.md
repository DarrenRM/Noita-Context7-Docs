---
title: Weather Configuration
category: data
---

# Weather Configuration

This document details the configuration for weather effects in Noita, primarily controlling visual aspects and atmospheric conditions.

## Key Attributes

The `<WeatherConfig>` element contains several attributes that influence the overall weather system.

| Attribute Name             | Description                                                                                                | Example Value |
| :------------------------- | :--------------------------------------------------------------------------------------------------------- | :------------ |
| `debug`                    | Enables debug mode for weather effects.                                                                    | `0`           |
| `autoplay`                 | Automatically starts weather effects when the game loads.                                                  | `1`           |
| `init_randomize`           | Randomizes initial weather conditions upon game start.                                                     | `1`           |
| `speed`                    | Controls the overall speed of weather animations and transitions.                                            | `0.005`       |
| `storm_alpha_0`            | The starting transparency of storm effects.                                                                | `0`           |
| `storm_alpha_1`            | The maximum transparency of storm effects.                                                                 | `0.6`         |
| `storm_clouds_pos_y_0`     | The starting Y-position for storm clouds.                                                                  | `130`         |
| `storm_clouds_pos_y_1`     | The ending Y-position for storm clouds.                                                                    | `40`          |
| `storm_value`              | A value that influences the intensity or presence of storms.                                               | `0`           |
| `time`                     | Represents the current time or progression within the weather cycle.                                       | `0.103977`    |
| `windspeed`                | The current speed and direction of the wind. Negative values typically indicate wind from right to left. | `-3.26618`    |
| `parallax_offset_y`        | Controls the vertical parallax effect for background elements.                                             | `50`          |
| `mountains_01_offset_y`    | Vertical offset for the first layer of mountains.                                                          | `39.49`       |
| `mountains_02_offset_y`    | Vertical offset for the second layer of mountains.                                                         | `42.74`       |
| `clouds_01_offset_y_min` | Minimum Y-position for the first cloud layer.                                                              | `-5`          |
| `clouds_01_offset_y_max` | Maximum Y-position for the first cloud layer.                                                              | `74`          |
| `clouds_02_offset_y_min` | Minimum Y-position for the second cloud layer.                                                             | `36.4`        |
| `clouds_02_offset_y_max` | Maximum Y-position for the second cloud layer.                                                             | `127`         |

```xml
<WeatherConfig 
	debug="0"
	autoplay="1" 
	init_randomize="1" 
	speed="0.005" 
	storm_alpha_0="0" 
	storm_alpha_1="0.6" 
	storm_clouds_pos_y_0="130" 
	storm_clouds_pos_y_1="40" 
	storm_value="0" 
	time="0.103977" 
	windspeed="-3.26618" 
	parallax_offset_y="50"
	mountains_01_offset_y="39.49"
	mountains_02_offset_y="42.74"
	clouds_01_offset_y_min="-5"
	clouds_01_offset_y_max="74"
	clouds_02_offset_y_min="36.4"
	clouds_02_offset_y_max="127"
	>
</WeatherConfig>
```