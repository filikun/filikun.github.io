---
layout: default
title: Entity chip
parent: 🦄 Dashboard UI
nav_order: 103
has_children: false
has_toc: true
---


```yaml
type: custom:mushroom-chips-card
chips:
  - type: template
    entity: input_boolean.test
    icon: mdi:motion-sensor
    tap_action:
      action: toggle
    content: >-
      {% set state = states('input_boolean.test') %} {% if state == 'on' %} På
      {% elif state == 'off' %} Av {% else %} Fel {% endif %}
    card_mod:
      style:
        .: |
          ha-card {
            {% if is_state('input_boolean.test', 'on') %}
               --chip-background: rgba(var(--blue-rgb));
            {% endif %}
            {% if is_state('input_boolean.test', 'on') %}
              --text-color: var(--black);
              --color: var(--black);
            {% else %}
              --text-color var(--contrast20);
              --color: var(--contrast20);
            {% endif %}
          }              
alignment: center
```