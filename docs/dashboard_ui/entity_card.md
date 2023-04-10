---
layout: default
title: Entity card
parent: 🦄 Dashboard UI
nav_order: 100
has_children: false
has_toc: true
---

# Entity card

## Card
```yaml
type: custom:decluttering-card
template: rounded_entity
variables:
  - name: Filip PC
  - entity: input_boolean.test
  - state: 'on'
  - action: toggle
  - color: rgba(var(--yellow-rgb));
```

## Template
```yaml
decluttering_templates:
  rounded_entity:
    card:
      type: custom:mushroom-template-card
      primary: '[[name]]'
      secondary: |-
        {%- if is_state(entity, '[[state]]') %} 
        På
        {%- else %}
        Av
        {% endif %}
      entity: '[[entity]]'
      tap_action:
        action: '[[action]]'
      icon_color: ''
      icon: mdi:desktop-classic
      card_mod:
        style:
          .: |
            ha-card {
                margin: auto;
              {% if is_state('[[entity]]', '[[state]]') %}
                 background: [[color]];
              {% endif %}
              {% if is_state('[[entity]]', '[[state]]') %}
                --primary-text-color: var(--black);;
                --secondary-text-color: var(--black);
              {% else %}
                --primary-text-color: var(--contrast20);
                --secondary-text-color: var(--contrast20);
              {% endif %}
            }
            mushroom-shape-icon {
              {% if is_state('[[entity]]', '[[state]]') %}
                --icon-color: var(--black)!important;
                --icon-color-disabled: var(--black)!important;
              {% else %};
                --icon-color: var(--contrast20)!important;
                --icon-color-disabled: var(--contrast20)!important;
              {% endif %}
            }
```