---
layout: default
title: Adaptive Lighting & night lights
parent: Lights
nav_order: 4
---

custom integration
{: .label .label-purple }

HACS
{: .label .label-blue }

# Adaptive Lighting & night lights
Makes the lights change brigtness and color temperature depending on the sun's placement on the sky. This integration also makes it easy to have a night light mode.

[Link to integration](https://github.com/basnijholt/adaptive-lighting)


<details open markdown="block">
  <summary>My settings</summary>

```yaml	  
lights: light.hallway_roof, light.hallway_window # select individual lights, not groups
initial_transition: 1
sleep_transition: 1
Transition time: 45
Interval: 90
min_brightness: 35
max_brightness 75
min_color_temp: 2000
max_color_temp: 5500
sleep_brightness: 1
sleep_color_temp: 1000
sunrise_time: none
sunrise_offset: 0
sunstet_time: none
sunset_offset: 0
only_once: []
take_over_control: []
detect_non_ha_changes: [x]
separate_turn_on_commands: []

```

</details>