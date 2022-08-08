---
layout: default
title: 🎨 Theme
parent: 🦄 Dashboard UI
nav_order: 2
has_children: false
has_toc: true
---

# Theme
Taking heavy inspiration of iOS dark mode this theme is split into one mobile and one desktop version. The big difference is the menu bar that is added on the mobile version.

<img src="\assets\images\theme\theme.png" height="300">

## Mobile

<details open markdown="block">
  <summary>Code</summary>

```yml
filikun-mobile:

# iOS colors 
  dark_label: rgba(255.0, 255.0, 255.0, 1.0)
  dark_secondaryLabel: rgba(235.0, 235.0, 245.0, 0.6)
  dark_tertiaryLabel: rgba(235.0, 235.0, 245.0, 0.3)
  dark_quaternaryLabel: rgba(235.0, 235.0, 245.0, 0.18)
  dark_systemFill: rgba(120.0, 120.0, 128.0, 0.36)
  dark_secondarySystemFill: rgba(120.0, 120.0, 128.0, 0.32)
  dark_tertiarySystemFill: rgba(118.0, 118.0, 128.0, 0.24)
  dark_quaternarySystemFill: rgba(118.0, 118.0, 128.0, 0.18)
  dark_placeholderText: rgba(235.0, 235.0, 245.0, 0.3)
  dark_systemBackground: rgba(0.0, 0.0, 0.0, 1.0)
  dark_secondarySystemBackground: rgba(28.0, 28.0, 30.0, 1.0)
  dark_tertiarySystemBackground: rgba(44.0, 44.0, 46.0, 1.0)
  dark_systemGroupedBackground: rgba(0.0, 0.0, 0.0, 1.0)
  dark_secondarySystemGroupedBackground: rgba(28.0, 28.0, 30.0, 1.0)
  dark_tertiarySystemGroupedBackground: rgba(44.0, 44.0, 46.0, 1.0)
  dark_separator: rgba(84.0, 84.0, 88.0, 0.6)
  dark_opaqueSeparator: rgba(56.0, 56.0, 58.0, 1.0)
  dark_link: rgba(9.0, 132.0, 255.0, 1.0)
  dark_darkText: rgba(0.0, 0.0, 0.0, 1.0)
  dark_lightText: rgba(255.0, 255.0, 255.0, 0.6)
  dark_systemBlue: rgba(10.0, 132.0, 255.0, 1.0)
  dark_systemGreen: rgba(48.0, 209.0, 88.0, 1.0)
  dark_systemIndigo: rgba(94.0, 92.0, 230.0, 1.0)
  dark_systemOrange: rgba(255.0, 159.0, 10.0, 1.0)
  dark_systemPink: rgba(255.0, 55.0, 95.0, 1.0)
  dark_systemPurple: rgba(191.0, 90.0, 242.0, 1.0)
  dark_systemRed: rgba(255.0, 69.0, 58.0, 1.0)
  dark_systemTeal: rgba(100.0, 210.0, 255.0, 1.0)
  dark_systemYellow: rgba(255.0, 214.0, 10.0, 1.0)
  dark_systemGray: rgba(142.0, 142.0, 147.0, 1.0)
  dark_systemGray2: rgba(99.0, 99.0, 102.0, 1.0)
  dark_systemGray3: rgba(72.0, 72.0, 74.0, 1.0)
  dark_systemGray4: rgba(58.0, 58.0, 60.0, 1.0)
  dark_systemGray5: rgba(44.0, 44.0, 46.0, 1.0)
  dark_systemGray6: rgba(28.0, 28.0, 30.0, 1.0)

  #iOS fonts
  primary-font-family: SF Pro Display
  paper-font-common-base_-_font-family: var(--primary-font-family)
  paper-font-common-code_-_font-family: var(--primary-font-family)
  paper-font-body1_-_font-family: var(--primary-font-family)
  paper-font-subhead_-_font-family: var(--primary-font-family)
  paper-font-headline_-_font-family: var(--primary-font-family)
  paper-font-caption_-_font-family: var(--primary-font-family)
  paper-font-title_-_font-family: var(--primary-font-family)
  ha-card-header-font-family: var(--primary-font-family)
  mdc-typography-body1-font-family: var(--primary-font-family)
  mdc-typography-font-family: var(--primary-font-family)   

# Universal

  # Header & footer:
  app-header-background-color: var(--dark_systemBackground)
  app-header-text-color: var(--dark_label)
  header-active-tab-color: var(--dark_systemBlue)
  header-all-tabs-color: var(--paper-item-icon-color)
  header-tab-indicator-color: 'rgba(0, 0, 0, 0)'
  header-background-color: var( --ha-card-background, var(--card-background-color, white) )
  footer-shadow: 0px -0.3px 0.3px 0px rgba(0,0,0,0.2)
  header-shadow: 0px 0.3px 0.3px 0px rgba(0,0,0,0.2)
  header-height: 78px

  # Main Interface Colors
  primary-color: var(--dark_systemBlue)
  light-primary-color: var(--dark_systemBlue)
  primary-background-color: var(--dark_systemBackground)
  secondary-background-color: var(--dark_secondarySystemBackground)
  divider-color: var(--dark_separator)
  accent-color: var(--dark_systemBlue)

  # Text
  primary-text-color: var(--dark_label)
  secondary-text-color: var(--dark_secondaryLabel)
  text-primary-color: var(--dark_label)
  disabled-text-color: var(--dark_secondaryLabel)

  # Sidebar Menu
  sidebar-icon-color: var(--dark_systemGray)
  sidebar-text-color: var(--dark_label)
  sidebar-background-color: var(--dark_secondarySystemBackground)
  sidebar-selected-background-color: var(--dark_systemBackground)
  sidebar-selected-icon-color: var(--dark_systemBlue)
  sidebar-selected-text-color: var(--sidebar-selected-icon-color)

  # Buttons
  paper-item-icon-color: var(--sidebar-icon-color)
  paper-item-icon-active-color: var(--dark_systemBlue)

  # States and Badges
  state-icon-color: var(--sidebar-icon-color)
  state-icon-active-color: var(--dark_systemBlue)
  state-icon-unavailable-color: var(--disabled-text-color)

  # Sliders
  paper-slider-knob-color: var(--dark_label)
  paper-slider-knob-start-color: var(--dark_label)
  paper-slider-pin-color: var(--dark_systemBlue)
  paper-slider-active-color: var(--paper-slider-pin-color)
  paper-slider-secondary-color: var(--paper-slider-pin-color)

  # Labels
  label-badge-background-color: var(--dark_secondarySystemBackground)
  label-badge-text-color: var(--dark_label)
  label-badge-red: var(--dark_systemRed)
  label-badge-green: var(--dark_systemGreen)
  label-badge-blue: var(--dark_systemBlue)
  label-badge-yellow: var(--dark_systemYellow)
  label-badge-gray: var(--dark_systemGray)

  # Cards
  card-background-color: var(--dark_secondarySystemBackground)
  ha-card-border-radius: "10px"
  ha-card-box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.16)
  paper-dialog-background-color: var(--dark_secondarySystemBackground)
  paper-listbox-background-color: var(--dark_secondarySystemBackground)
  paper-card-background-color: var(--dark_secondarySystemBackground)

  # Switches
  switch-checked-button-color: var(--dark_label)
  switch-checked-track-color:  var(--dark_systemGreen)
  switch-unchecked-button-color: var(--dark_label)
  switch-unchecked-track-color: var(--dark_systemGray2)

  # Toggles
  paper-toggle-button-checked-button-color: var(--dark_label)
  paper-toggle-button-checked-bar-color: var(--dark_systemGreen)
  paper-toggle-button-unchecked-button-color: var(--dark_label)
  paper-toggle-button-unchecked-bar-color: var(--dark_systemGray2)

  # Table
  table-row-background-color: var(--dark_secondarySystemBackground)
  table-row-alternative-background-color: var(--dark_tertiarySystemBackground)
  data-table-background-color: var(--dark_systemBackground)

  # Dropdowns
  material-background-color: var(--dark_secondarySystemBackground)
  material-secondary-background-color: var(--dark_tertiarySystemBackground)
  mdc-theme-surface: var(--dark_secondarySystemBackground)

  # Pre/Code
  markdown-code-background-color: var(--dark_systemFill)

  # Checkboxes
  mdc-checkbox-unchecked-color: var(--dark_systemFill)
  mdc-checkbox-disable-color: var(--dark_secondaryLabel)
  mdc-select-fill-color: var(--dark_secondarySystemBackground)
  mdc-select-ink-color: var(--dark_label)
  mdc-select-label-ink-color: var(--dark_secondaryLabel)
  mdc-select-idle-line-color: var(--dark_label)
  mdc-select-dropdown-icon-color: var(--dark_secondaryLabel)
  mdc-select-hover-line-color: var(--dark_systemBlue)

  # Input
  input-fill-color: var(--dark_secondarySystemBackground)
  input-dropdown-icon-color: var(--dark_secondaryLabel)
  input-ink-color: var(--dark_label)
  input-label-ink-color: var(--dark_secondaryLabel)
  input-idle-line-color: var(--dark_label)
  input-hover-line-color: var(--dark_systemBlue)

  # Mushroom specific
  mush-chip-spacing: 8px
  mush-chip-padding: 0 0.25em
  mush-chip-height: 36px
  mush-chip-border-radius: 18px
  mush-chip-font-size: 0.35em
  mush-chip-font-weight: bold
  mush-chip-icon-size: 0.5em
  mush-chip-avatar-padding: 0.5em
  mush-chip-avatar-border-radius: 50%

  # Colors
  mush-rgb-red: 255, 69, 58
  mush-rgb-pink: 255, 55, 95
  mush-rgb-purple: 191, 90, 242
  mush-rgb-indigo: 94, 92, 230
  mush-rgb-blue: 10, 132, 255
  mush-rgb-teal: 100, 210, 255
  mush-rgb-green: 48, 209, 88
  mush-rgb-yellow: 255, 214, 10
  mush-rgb-orange: 255, 159, 10
  mush-rgb-deep-orange: 255, 87, 34
  mush-rgb-grey: 209, 209, 214
  mush-rgb-black: 0, 0, 0
  mush-rgb-white: 255, 255, 255

# Card-Mod
  card-mod-theme: "filikun-mobile"

  card-mod-more-info-yaml: |
    $: |
      .mdc-dialog {
        backdrop-filter: blur(17px);
        -webkit-backdrop-filter: blur(17px);
        background: rgba(0,0,0,0.25);
      }
      .mdc-dialog .mdc-dialog__container .mdc-dialog__surface {
        background: none !important;
        box-shadow: none;
        border-radius: 0px;
      }
  card-mod-root-yaml: |
    ha-tabs$: |
      #tabsContent {
        width: 97%;
        height: 44px;
      }
    .: |
      @media (orientation: portrait) {
        a.menu-link[target="_blank"], ha-button-menu, ha-menu-button, [main-title] {
          display: none !important;
        }
        app-toolbar {
          padding-right: 0px;
          padding-left: 0px;
        }
      }
      app-header {
        top: auto !important;
        bottom: 0 !important;
        transform: unset !important;
        box-shadow: var(--footer-shadow) !important;
        height: var(--header-height) !important;
        background-color: var(--header-background-color) !important;
      }
      app-toolbar {
        transform: none !important;
        height: 44px !important;
        background-color: var(--header-background-color) !important;
      }
      #view {
        min-height: 100% !important;
        margin-top: -80px !important;
      }
      ha-tabs {
        --paper-tabs-selection-bar-color: var(--header-tab-indicator-color) !important;
        --mdc-icon-size: 28px;
      }
      paper-tab[aria-selected=true] {
        color: var(--header-active-tab-color) !important;
      }
      paper-tab {
        padding-left: 0px;
        padding-right: 0px;
        width: calc(100% / 3);
        color: var(--header-all-tabs-color) !important;
      }
  card-mod-view-yaml: |
    "*:first-child$": |
      #columns .column > * {
        padding-left: 5px;
        padding-right: 5px;
        padding-bottom: 5px;
      }
    grid-layout$: |
      #root {
        margin-left: 5px !important;
        margin-right: 5px !important;
      }
```
</details>  


## Desktop

<details open markdown="block">
  <summary>Code</summary>

```yml
filikun-desktop:

# iOS colors 
  dark_label: rgba(255.0, 255.0, 255.0, 1.0)
  dark_secondaryLabel: rgba(235.0, 235.0, 245.0, 0.6)
  dark_tertiaryLabel: rgba(235.0, 235.0, 245.0, 0.3)
  dark_quaternaryLabel: rgba(235.0, 235.0, 245.0, 0.18)
  dark_systemFill: rgba(120.0, 120.0, 128.0, 0.36)
  dark_secondarySystemFill: rgba(120.0, 120.0, 128.0, 0.32)
  dark_tertiarySystemFill: rgba(118.0, 118.0, 128.0, 0.24)
  dark_quaternarySystemFill: rgba(118.0, 118.0, 128.0, 0.18)
  dark_placeholderText: rgba(235.0, 235.0, 245.0, 0.3)
  dark_systemBackground: rgba(0.0, 0.0, 0.0, 1.0)
  dark_secondarySystemBackground: rgba(28.0, 28.0, 30.0, 1.0)
  dark_tertiarySystemBackground: rgba(44.0, 44.0, 46.0, 1.0)
  dark_systemGroupedBackground: rgba(0.0, 0.0, 0.0, 1.0)
  dark_secondarySystemGroupedBackground: rgba(28.0, 28.0, 30.0, 1.0)
  dark_tertiarySystemGroupedBackground: rgba(44.0, 44.0, 46.0, 1.0)
  dark_separator: rgba(84.0, 84.0, 88.0, 0.6)
  dark_opaqueSeparator: rgba(56.0, 56.0, 58.0, 1.0)
  dark_link: rgba(9.0, 132.0, 255.0, 1.0)
  dark_darkText: rgba(0.0, 0.0, 0.0, 1.0)
  dark_lightText: rgba(255.0, 255.0, 255.0, 0.6)
  dark_systemBlue: rgba(10.0, 132.0, 255.0, 1.0)
  dark_systemGreen: rgba(48.0, 209.0, 88.0, 1.0)
  dark_systemIndigo: rgba(94.0, 92.0, 230.0, 1.0)
  dark_systemOrange: rgba(255.0, 159.0, 10.0, 1.0)
  dark_systemPink: rgba(255.0, 55.0, 95.0, 1.0)
  dark_systemPurple: rgba(191.0, 90.0, 242.0, 1.0)
  dark_systemRed: rgba(255.0, 69.0, 58.0, 1.0)
  dark_systemTeal: rgba(100.0, 210.0, 255.0, 1.0)
  dark_systemYellow: rgba(255.0, 214.0, 10.0, 1.0)
  dark_systemGray: rgba(142.0, 142.0, 147.0, 1.0)
  dark_systemGray2: rgba(99.0, 99.0, 102.0, 1.0)
  dark_systemGray3: rgba(72.0, 72.0, 74.0, 1.0)
  dark_systemGray4: rgba(58.0, 58.0, 60.0, 1.0)
  dark_systemGray5: rgba(44.0, 44.0, 46.0, 1.0)
  dark_systemGray6: rgba(28.0, 28.0, 30.0, 1.0)

  #iOS fonts
  primary-font-family: SF Pro Text
  paper-font-common-base_-_font-family: var(--primary-font-family)
  paper-font-common-code_-_font-family: var(--primary-font-family)
  paper-font-body1_-_font-family: var(--primary-font-family)
  paper-font-subhead_-_font-family: var(--primary-font-family)
  paper-font-headline_-_font-family: var(--primary-font-family)
  paper-font-caption_-_font-family: var(--primary-font-family)
  paper-font-title_-_font-family: var(--primary-font-family)
  ha-card-header-font-family: var(--primary-font-family)
  mdc-typography-body1-font-family: var(--primary-font-family)
  mdc-typography-font-family: var(--primary-font-family)    

# Universal

  # Header:
  app-header-background-color: var(--dark_systemBackground)
  app-header-text-color: var(--dark_label)

  # Main Interface Colors
  primary-color: var(--dark_systemBlue)
  light-primary-color: var(--dark_systemBlue)
  primary-background-color: var(--dark_systemBackground)
  secondary-background-color: var(--dark_secondarySystemBackground)
  divider-color: var(--dark_separator)
  accent-color: var(--dark_systemBlue)

  # Text
  primary-text-color: var(--dark_label)
  secondary-text-color: var(--dark_secondaryLabel)
  text-primary-color: var(--dark_label)
  disabled-text-color: var(--dark_secondaryLabel)

  # Sidebar Menu
  sidebar-icon-color: var(--dark_systemGray)
  sidebar-text-color: var(--dark_label)
  sidebar-background-color: var(--dark_secondarySystemBackground)
  sidebar-selected-background-color: var(--dark_systemBackground)
  sidebar-selected-icon-color: var(--dark_systemBlue)
  sidebar-selected-text-color: var(--sidebar-selected-icon-color)

  # Buttons
  paper-item-icon-color: var(--sidebar-icon-color)
  paper-item-icon-active-color: var(--dark_systemBlue)

  # States and Badges
  state-icon-color: var(--sidebar-icon-color)
  state-icon-active-color: var(--dark_systemBlue)
  state-icon-unavailable-color: var(--disabled-text-color)

  # Sliders
  paper-slider-knob-color: var(--dark_label)
  paper-slider-knob-start-color: var(--dark_label)
  paper-slider-pin-color: var(--dark_systemBlue)
  paper-slider-active-color: var(--paper-slider-pin-color)
  paper-slider-secondary-color: var(--paper-slider-pin-color)

  # Labels
  label-badge-background-color: var(--dark_secondarySystemBackground)
  label-badge-text-color: var(--dark_label)
  label-badge-red: var(--dark_systemRed)
  label-badge-green: var(--dark_systemGreen)
  label-badge-blue: var(--dark_systemBlue)
  label-badge-yellow: var(--dark_systemYellow)
  label-badge-gray: var(--dark_systemGray)

  # Cards
  card-background-color: var(--dark_secondarySystemBackground)
  ha-card-border-radius: "10px"
  ha-card-box-shadow: 0px 2px 4px 0px rgba(0,0,0,0.16)
  paper-dialog-background-color: var(--dark_secondarySystemBackground)
  paper-listbox-background-color: var(--dark_secondarySystemBackground)
  paper-card-background-color: var(--dark_secondarySystemBackground)

  # Switches
  switch-checked-button-color: var(--dark_label)
  switch-checked-track-color:  var(--dark_systemGreen)
  switch-unchecked-button-color: var(--dark_label)
  switch-unchecked-track-color: var(--dark_systemGray2)

  # Toggles
  paper-toggle-button-checked-button-color: var(--dark_label)
  paper-toggle-button-checked-bar-color: var(--dark_systemGreen)
  paper-toggle-button-unchecked-button-color: var(--dark_label)
  paper-toggle-button-unchecked-bar-color: var(--dark_systemGray2)

  # Table
  table-row-background-color: var(--dark_secondarySystemBackground)
  table-row-alternative-background-color: var(--dark_tertiarySystemBackground)
  data-table-background-color: var(--dark_systemBackground)

  # Dropdowns
  material-background-color: var(--dark_secondarySystemBackground)
  material-secondary-background-color: var(--dark_tertiarySystemBackground)
  mdc-theme-surface: var(--dark_secondarySystemBackground)

  # Pre/Code
  markdown-code-background-color: var(--dark_systemFill)

  # Checkboxes
  mdc-checkbox-unchecked-color: var(--dark_systemFill)
  mdc-checkbox-disable-color: var(--dark_secondaryLabel)
  mdc-select-fill-color: var(--dark_secondarySystemBackground)
  mdc-select-ink-color: var(--dark_label)
  mdc-select-label-ink-color: var(--dark_secondaryLabel)
  mdc-select-idle-line-color: var(--dark_label)
  mdc-select-dropdown-icon-color: var(--dark_secondaryLabel)
  mdc-select-hover-line-color: var(--dark_systemBlue)

  # Input
  input-fill-color: var(--dark_secondarySystemBackground)
  input-dropdown-icon-color: var(--dark_secondaryLabel)
  input-ink-color: var(--dark_label)
  input-label-ink-color: var(--dark_secondaryLabel)
  input-idle-line-color: var(--dark_label)
  input-hover-line-color: var(--dark_systemBlue)

  # Mushroom layout
  mush-spacing: 12px  

  # Mushroom Chip
  mush-chip-spacing: 8px
  mush-chip-padding: 0 0.25em
  mush-chip-height: 36px
  mush-chip-border-radius: 18px
  mush-chip-font-size: 0.35em
  mush-chip-font-weight: bold
  mush-chip-icon-size: 0.5em
  mush-chip-avatar-padding: 0.5em
  mush-chip-avatar-border-radius: 50%

  # Mushroom Title
  mush-title-padding: 24px 12px 16px
  mush-title-spacing: 12px
  mush-title-font-size: 24px
  mush-title-font-weight: normal
  mush-title-line-height: 1.2

  # Mushroom Subtitle
  mush-subtitle-font-size: 16px
  mush-subtitle-font-weight: normal
  mush-subtitle-line-height: 1.2

  # Mushroom Card
  mush-card-primary-font-size: 14px
  mush-card-secondary-font-size: 12px
  mush-card-primary-font-weight: bold
  mush-card-secondary-font-weight: bolder
  mush-card-primary-line-height: 1.5
  mush-card-secondary-line-height: 1.5

  # Mushroom Colors
  mush-rgb-red: 255, 69, 58
  mush-rgb-pink: 255, 55, 95
  mush-rgb-purple: 191, 90, 242
  mush-rgb-indigo: 94, 92, 230
  mush-rgb-blue: 10, 132, 255
  mush-rgb-teal: 100, 210, 255
  mush-rgb-green: 48, 209, 88
  mush-rgb-yellow: 255, 214, 10
  mush-rgb-orange: 255, 159, 10
  mush-rgb-deep-orange: 255, 87, 34
  mush-rgb-grey: 209, 209, 214
  mush-rgb-black: 0, 0, 0
  mush-rgb-white: 255, 255, 255

# Card-Mod
  card-mod-theme: "filikun-desktop"

  card-mod-more-info-yaml: |
    $: |
      .mdc-dialog__scrim {
        backdrop-filter: blur(20px) brightness(70%);
        -webkit-backdrop-filter: blur(20px) brightness(70%);
      }        
      .mdc-dialog .mdc-dialog__container .mdc-dialog__surface {
        border-radius: 30px;
        background: var(--primary-background-color);
      }   
  card-mod-root-yaml: |
      app-header {
        top: auto !important;
        bottom: 0 !important;
        transform: unset !important;
        box-shadow: var(--footer-shadow) !important;
        height: var(--header-height) !important;
        background-color: var(--header-background-color) !important;
      }
      app-toolbar {
        transform: none !important;
        height: 44px !important;
        background-color: var(--header-background-color) !important;
      }
      #view {
        min-height: 100% !important;
        margin-top: -80px !important;
      }
      ha-tabs {
        --paper-tabs-selection-bar-color: var(--divider-color) !important;
        --mdc-icon-size: 28px;
      }
      paper-tab[aria-selected=true] {
        color: var(--primary-color) !important;
      }
      paper-tab {
        padding-left: 0px;
        padding-right: 0px;
        width: calc(100% / 3);
        color: var(--paper-item-icon-color) !important;
      }
  card-mod-view-yaml: |
    "*:first-child$": |
      #columns .column > * {
        padding-left: 5px;
        padding-right: 5px;
        padding-bottom: 5px;
      }
    grid-layout$: |
      #root {
        margin-left: 10px !important;
        margin-right: 10px !important;
      }
```
</details>  