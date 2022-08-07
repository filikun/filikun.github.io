---
layout: default
title: Computer controlled lights
parent: Lights
nav_order: 6
---

Automation
{: .label .label-green }

# Computer controlled lights
Will turn the lights on when a computer in a group is `home` and also disable motion control for that room.

<details open markdown="block">
  <summary>Manual control</summary>
```yml	
Type: input_boolean
Name: Light condition office computer
```
</details>

<details open markdown="block">
  <summary>Automation code</summary>
{% raw %}
```yml
alias: 💡💻Office lights routine
description: >-
  Turns lights on in the office when computers are on and prevent motion sensor
  from turning lights off
trigger:
  - platform: state
    entity_id: group.presence_computers
    to: home
    id: computer_on
  - platform: state
    entity_id: group.presence_computers
    id: computer_off
    to: not_home
    for:
      hours: 0
      minutes: 0
      seconds: 10
condition:
  - condition: state
    entity_id: input_boolean.guest_mode
    state: "off"
  - condition: state
    entity_id: input_boolean.light_condition_office_computer
    state: "on"
action:
  - choose:
      - conditions:
          - condition: trigger
            id: computer_on
        sequence:
          - service: light.turn_on
            target:
              entity_id: light.office_shelf
            data: {}
      - conditions:
          - condition: trigger
            id: computer_off
        sequence:
          - service: light.turn_off
            target:
              entity_id:
                - light.office_shelf
            data: {}
          - service: light.turn_off
            target:
              entity_id: light.office_window
            data: {}
    default: []
mode: restart
```
{% endraw %}
</details>

