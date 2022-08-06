---
layout: default
title: Gatulampa
parent: Lights
nav_order: 3
---


# Gatulampa



# A collapsible section with markdown
<details>
  <summary>Click to expand!</summary>
  
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
