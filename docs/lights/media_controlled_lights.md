---
layout: default
title: Media controlled lights
parent: Lights
nav_order: 5
---

Automation
{: .label .label-green }

# Media controlled lights
Automation that looks at what Apple TV is doing and change the lights depending on it's state. The lights will turn off when playing and on when pausing or turning the Apple TV off. When playing it also turns our motion control off so that motion will not trigger the lights on again.

<details open markdown="block">
  <summary>Manual control</summary>
```yml	
Type: input_boolean
Name: Livingroom_tv_activated_lights
```
</details>

<details open markdown="block">
  <summary>Automation code</summary>
{% raw %}
```yml
alias: "💡📺 Livingroom lights routine "
description: Turns the lights on/off based on TV state
trigger:
  - platform: state
    entity_id: media_player.apple_tv
    id: tv_standby
    to: standby
    for:
      hours: 0
      minutes: 1
      seconds: 0
  - platform: state
    entity_id: media_player.apple_tv
    id: tv_idle
    to: idle
    for:
      hours: 0
      minutes: 1
      seconds: 0
  - platform: state
    entity_id: media_player.apple_tv
    id: tv_paused
    to: paused
    for:
      hours: 0
      minutes: 0
      seconds: 5
  - platform: state
    entity_id: media_player.apple_tv
    id: tv_playing
    to: playing
    for:
      hours: 0
      minutes: 0
      seconds: 5
condition:
  - condition: state
    entity_id: input_boolean.night_mode
    state: "off"
  - condition: state
    entity_id: input_boolean.livingroom_tv_activated_lights
    state: "on"
action:
  - choose:
      - conditions:
          - condition: trigger
            id: tv_playing
        sequence:
          - service: input_boolean.turn_off
            target:
              entity_id: input_boolean.livingroom_motion_activated_lights
            data: {}
          - service: light.turn_off
            target:
              entity_id: light.livingroom
            data: {}
      - conditions:
          - condition: or
            conditions:
              - condition: trigger
                id: tv_standby
              - condition: trigger
                id: tv_idle
        sequence:
          - choose:
              - conditions:
                  - condition: numeric_state
                    entity_id: sensor.motion_sensor_livingroom_illuminance_lux
                    below: input_number.livingroom_motion_activated_lights_brightness
                sequence:
                  - service: light.turn_on
                    data: {}
                    target:
                      entity_id:
                        - light.livingroom_reading
                        - light.livingroom_window_left
                        - light.livingroom_window_right
                  - service: input_boolean.turn_on
                    data: {}
                    target:
                      entity_id: input_boolean.livingroom_motion_activated_lights
            default: []
          - service: input_boolean.turn_on
            target:
              entity_id: input_boolean.livingroom_motion_activated_lights
            data: {}
      - conditions:
          - condition: trigger
            id: tv_paused
        sequence:
          - choose:
              - conditions:
                  - condition: numeric_state
                    entity_id: sensor.motion_sensor_livingroom_illuminance_lux
                    below: input_number.livingroom_motion_activated_lights_brightness
                sequence:
                  - service: light.turn_on
                    data: {}
                    target:
                      entity_id:
                        - light.livingroom_roof_table
                        - light.livingroom_reading
            default: []
    default: []
mode: parallel
max: 3
```
{% endraw %}
</details>

