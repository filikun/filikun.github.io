---
layout: default
title: 🔘 iOS button
parent: 🍏 iOS Theme
grand_parent: 🦄 Dashboard UI
nav_order: 1
has_children: false
has_toc: false
---
!-- markdownlint-disable MD046 --

## Description

![Image title](../../assets/images/theme/ios_theme/ios_theme_front.jpeg){ width="500" }

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

??? note "Template Code"

    ```yaml title="ios-button.yaml"
    --8<-- "ios_theme_templates/ios-button/ios-button.yaml"
    ```