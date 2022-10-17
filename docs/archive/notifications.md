---
layout: default
title: 📱 Notifications
parent: 📖 Archive
nav_order: 1
has_children: true
has_toc: true
---

Automation
{: .label .label-green }

# Notify with repeat

<details open markdown="block">
  <summary>Manual control</summary>

```yml	
Type: input_boolean
Name: Name notify
```
</details>

<details open markdown="block">
  <summary>Automation code</summary>
{% raw %}

```yml
alias: 📱💊 Notify name meds
description: ""
trigger:
  - platform: time
    at: "08:00:00"
  - platform: time
    at: "12:05:00"
condition:
  - condition: state
    entity_id: input_boolean.name_notify
    state: "on"
action:
  - variables:
      ja: "{{ 'JA_' ~ context.id }}"
  - repeat:
      while:
        - condition: state
          entity_id: input_boolean.name_notify
          state: "on"
      sequence:
        - service: notify.mobile_app_name_iphone
          data:
            message: Har du redan tagit den?
            data:
              tag: name_tablett
              actions:
                - action: "{{ ja }}"
                  title: Ja
            title: 💊 Dags att ta tablett
        - choose:
            - conditions:
                - condition: state
                  entity_id: device_tracker.name_pc
                  state: home
              sequence:
                - service: notify.name_pc
                  data:
                    message: Har du redan tagit den?
                    data:
                      duration: 10
                    title: 💊 Dags att ta tablett
          default: []
        - wait_for_trigger:
            platform: event
            event_type: mobile_app_notification_action
            event_data:
              action: "{{ ja }}"
          timeout: "00:30:00"
        - choose:
            - conditions:
                - condition: template
                  value_template: "{{ wait.trigger == none }}"
              sequence: []
            - conditions:
                - condition: template
                  value_template: "{{ wait.trigger.event.data.action == ja }}"
              sequence:
                - service: input_boolean.turn_off
                  target:
                    entity_id: input_boolean.name_notify
                  data: {}
                - service: notify.mobile_app_name_iphone
                  data:
                    message: clear_notification
                    data:
                      tag: name_tablett
          default: []
mode: restart
```
{% endraw %}
</details>
