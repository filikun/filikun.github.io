---
layout: default
title: Motion controlled lights
parent: Lights
nav_order: 3
---


# Motion controlled lights
This automation aims at turning on the lights if the light target is below the set level by the `input number` and our `input_boolean` is not off. It then turns off when motion is cleared and after our delay caused by a `input number`.

### Requirements 
- Smart light bulbs 
- Motion sensor (with motion & lux sensor)
- Input number to control brightness target
- input number to control delay after motion is off
- Input boolean for manual control


<details>
  <summary>Timer</summary>
<div class="code-example" markdown="1">
```yaml	  
Type: input_number
Name: hallway motion activated lights timer
Minimum value: 0
Maximum value: 60
Display mode: Input field
Step size: 1
Unit of measurement: min
```
</details>

<details>
  <summary>Light target</summary>
<div class="code-example" markdown="1">
```yaml	
Type: input_number
Name: Bathroom motion activated lights brightness
Minimum value: 0
Maximum value: 300
Display mode: Input field
Step size: 50
Unit of measurement: lx
```
</div>
</details>

<details>
  <summary>Manual control</summary>
<div class="code-example" markdown="1">
```yaml	
Type: input_boolean
Name: Hallway motion activated lights
```
</div>
</details>

<details>
  <summary>Automation code</summary>
<div class="code-example" markdown="1">
```yaml
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
                {{ states('input_number.hallway_motion_activated_lights_timer')
                | int }}
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
</div>
</details>
