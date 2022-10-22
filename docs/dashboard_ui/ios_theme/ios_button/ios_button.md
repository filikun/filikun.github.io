---
layout: default
title: 🔘 iOS button
parent: 🍏 iOS Theme
grand_parent: 🦄 Dashboard UI
nav_order: 1
has_children: false
has_toc: false
---

## iOS button

![Image title](\assets\images\ios_templates\ios_button.png)


## Variables

| Variable                              | Notes                                                  |
| ------------------------------------- | ------------------------------------------------------ |
| title                                 |                                                        |
| icon                                  |                                                        |
| icon_background                       | Color around icon                                      |
| entity                                |                                                        | 


## Usage

```yaml
- type: custom:button-card
  variables:
    title: "Hall"
    icon: mdi:shoe-formal
    icon_background: "pink"
    entity: automation.light_motion_hallway
  template:
    - ios_button
```