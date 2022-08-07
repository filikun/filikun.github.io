---
layout: default
title: Motion controlled lights
parent: Lights
nav_order: 3
---

Automation
{: .label .label-green }

# Motion controlled lights
This automation aims at turning on the lights if the light target is below the set level by the `input number` and our `input_boolean` is not off. It then turns off when motion is cleared and after our delay caused by a `input number`.


<details open markdown="block">
  <summary>Timer</summary>
```yml  
Type: input_number
Name: hallway motion activated lights timer
Minimum value: 0
Maximum value: 60
Display mode: Input field
Step size: 1
Unit of measurement: min
```
</details>

<details open markdown="block">
  <summary>Light target</summary>
```yml
Type: input_number
Name: Bathroom motion activated lights brightness
Minimum value: 0
Maximum value: 300
Display mode: Input field
Step size: 50
Unit of measurement: lx
```
</details>

<details open markdown="block">
  <summary>Manual control</summary>
```yml	
Type: input_boolean
Name: Hallway motion activated lights
```
</details>

<details open markdown="block">
  <summary>Automation code</summary>
{% raw %}
```yml
alias: 💡 Belysning hall rörelse
description: ""
trigger:
  - platform: state
    entity_id: binary_sensor.motion_sensor_hallway_occupancy
    to: "on"
    id: "on"
  - platform: state
    entity_id: binary_sensor.motion_sensor_hallway_occupancy
    to: "off"
    id: "off"
condition:
  - condition: state
    entity_id: input_boolean.hallway_motion_activated_lights
    state: "on"
action:
  - choose:
      - conditions:
          - condition: trigger
            id: "on"
          - condition: or
            conditions:
              - condition: state
                entity_id: light.hallway
                state: "on"
              - condition: numeric_state
                entity_id: sensor.motion_sensor_hallway_illuminance_lux
                below: input_number.hallway_motion_activated_lights_brightness
        sequence:
          - service: light.turn_on
            target:
              entity_id:
                - light.hallway_roof
                - light.hallway_window
            data: {}
      - conditions:
          - condition: trigger
            id: "off"
        sequence:
          - delay:
              minutes: >-
                {{ states('input_number.hallway_motion_activated_lights_timer')| int }}
          - condition: state
            entity_id: input_boolean.hallway_motion_activated_lights
            state: "on"
          - service: light.turn_off
            target:
              entity_id:
                - light.hallway_roof
                - light.hallway_window
            data: {}
    default: []
mode: restart
```
{% endraw %}
</details>

