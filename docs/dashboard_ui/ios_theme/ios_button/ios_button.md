---
layout: default
title: 🔘 iOS button
parent: 🍏 iOS Theme
grand_parent: 🦄 Dashboard UI
nav_order: 1
has_children: false
has_toc: false
---

## Description

![Image title](\assets\images\theme\ios_theme\ios_theme_front.jpeg){ width="500" }

Card description should be here.

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

## Template

 <link rel="stylesheet" href="https://github.com/filikun/filikun.github.io/blob/5a55d739d2d2f3e0299ecd76bf7efc1115dbc775/docs/ios_theme_templates/ios-button/ios-button.yaml" type="text/yaml" />


