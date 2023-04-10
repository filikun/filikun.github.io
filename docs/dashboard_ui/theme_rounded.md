---
layout: default
title: Theme
parent: 🦄 Dashboard UI
nav_order: 101
has_children: false
has_toc: true
---


```yaml
Filikun Theme Rounded:

  ########################################################
  ############### Default global variables ###############
  ########################################################

  # Spacings and radius
  horizontal-stack-card-margin: 0px 8px
  vertical-stack-card-margin: 8px 0px
  grid-card-gap: 16px
  ha-card-border-width: "0px" # Removes default 1px line
  ha-card-border-radius: 24px
  masonry-view-card-margin: 40px 20px

  # Main Interface Colors
  primary-color: var(--blue)
  accent-color: var(--blue)
  primary-background-color: var(--contrast1)
  secondary-background-color: var(--contrast2)
  divider-color: var(--contrast3)

  # Text
  primary-text-color: var(--contrast20)
  secondary-text-color: var(--contrast9)
  text-primary-color: var(--contrast20)
  disabled-text-color: var(--contrast6)
  text-accent-color: var(--contrast1)

  # Header:
  app-header-background-color: var(--contrast1)
  app-header-text-color: var(--contrast20)
  app-header-selection-bar-color: transparant
  app-header-edit-background-color: var(--contrast2)
  app-header-edit-text-color: var(--contrast20)

  # Cards
  card-background-color: var(--contrast2)
  ha-card-background: var(--contrast2)
  ha-card-border-color: var(--contrast6)
  paper-listbox-background-color: var(--contrast3)

  # Tile card
  state-unavailable-color: var(--contrast6)
  state-light-off-color: var(--contrast10)
  state-light-on-color: var(--yellow)

  # Sidebar Menu
  sidebar-icon-color: var(--contrast6)
  sidebar-text-color: var(--contrast20)
  sidebar-background-color: var(--contrast2)
  sidebar-selected-icon-color: var(--blue)
  sidebar-selected-text-color: var(--blue)

  # Buttons
  paper-item-icon-color: var(--contrast9)
  mdc-button-outline-color: var(--contrast6)

  # States and Badges
  state-icon-color: var(--contrast9)

  # Sliders
  paper-slider-knob-color: var(--contrast20)
  paper-slider-knob-start-color: var(--contrast15)
  paper-slider-pin-color: var(--contrast5)
  paper-slider-pin-start-color: var(--contrast4)
  paper-slider-active-color: var(--contrast15)
  paper-slider-secondary-color: var(--contrast7)
  paper-slider-container-color: var(--contrast5)

  # Switches
  switch-checked-button-color: var(--green)
  switch-checked-track-color: var(--green)
  switch-unchecked-button-color: var(--contrast9)
  switch-unchecked-track-color: var(--contrast6)

  # Toggles
  paper-toggle-button-checked-button-color: var(--switch-checked-button-color)
  paper-toggle-button-checked-bar-color: var(--switch-checked-track-color)
  paper-toggle-button-unchecked-button-color: var(--switch-unchecked-button-color)
  paper-toggle-button-unchecked-bar-color: var(--switch-unchecked-track-color)

  # Table
  table-row-background-color: var(--contrast2)
  table-row-alternative-background-color: var(--contrast3)
  data-table-background-color: var(--contrast1)
  mdc-text-field-fill-color: var(--contrast3)

  # Input
  input-fill-color: var(--contrast3)
  input-dropdown-icon-color: var(--contrast9)
  material-background-color: var(--contrast2)
  input-ink-color: var(--contrast20)
  input-label-ink-color: var(--contrast9)
  input-idle-line-color: var(--contrast7)
  input-hover-line-color: var(--contrast20)
  mdc-select-fill-color: var(--input-fill-color)
  mdc-select-ink-color: var(--input-ink-color)
  mdc-select-label-ink-color: var(--input-label-ink-color)
  mdc-select-idle-line-color: var(--input-idle-line-color)
  mdc-select-dropdown-icon-color: var(--input-dropdown-icon-color)
  mdc-select-hover-line-color: var(--input-hover-line-color)
  mdc-text-field-disabled-fill-color: var(--contrast3)
  # Modal screen
  mdc-theme-surface: var(--contrast2)
  # Checkboxes
  mdc-checkbox-unchecked-color: var(--contrast15)

  # Colors
  orange-color: var(--orange)
  green-color: var(--green)
  blue-color: var(--blue)
  red-color: var(--red)
  purple-color: var(--purple)
  yellow-color: var(--yellow)
  grey-color: var(--contrast10)


  #######################################################
  ############### Custom global variables ###############
  #######################################################

  # Black / White
  black: "#000000"
  white: "#FFFFFF"
  # Colors
  purple: rgb(var(--purple-rgb))
  yellow: rgb(var(--yellow-rgb))
  orange: rgb(var(--orange-rgb))
  red: rgb(var(--red-rgb))
  green: rgb(var(--green-rgb))
  blue: rgb(var(--blue-rgb))
  # Color tints
  purple-tint: rgba(var(--purple-rgb),var(--color-tint))
  yellow-tint: rgba(var(--yellow-rgb),var(--color-tint))
  orange-tint: rgba(var(--orange-rgb),var(--color-tint))
  red-tint: rgba(var(--red-rgb),var(--color-tint))
  green-tint: rgba(var(--green-rgb),var(--color-tint))
  blue-tint: rgba(var(--blue-rgb),var(--color-tint))
  # Gradients
  brightness: linear-gradient(90deg, rgba(var(--brightness-low-rgb), 0.4) 0%, rgba(var(--brightness-high-rgb), 1) 100%)
  brightness-tint: linear-gradient(90deg, rgba(var(--brightness-low-rgb), 0.06) 0%, rgba(var(--brightness-high-rgb), var(--color-tint)) 100%)
  temperature: linear-gradient(90deg, rgba(var(--temperature-low-rgb), 01) 0%, rgba(var(--temperature-high-rgb), 1) 100%)
  temperature-tint: linear-gradient(90deg, rgba(var(--temperature-low-rgb), var(--color-tint)) 0%, rgba(var(--temperature-high-rgb), var(--color-tint)) 100%)
  # Color RGB variables
  purple-rgb: 239, 177, 255
  yellow-rgb: 255, 218, 120
  orange-rgb: 255, 181, 129
  red-rgb: 255, 145, 138
  green-rgb: 206, 245, 149
  blue-rgb: 144, 191, 255

  # Gradient RGB variables
  brightness-low-rgb: 232, 176, 29
  brightness-high-rgb: 255, 211, 94
  temperature-low-rgb: 177, 197, 255
  temperature-high-rgb: 255, 175, 131
  # Contrast variables
  black1: "#000000"
  black2: "#111318"
  black3: "#171A21"
  black4: "#1C1F27"
  black5: "#262A35"
  black6: "#353946"
  black7: "#434856"
  black8: "#535865"
  black9: "#636774"
  black10: "#777A83"
  white10: "#898C94"
  white9: "#969AA6"
  white8: "#A4A9B6"
  white7: "#B3B8C6"
  white6: "#C3C8D5"
  white5: "#D4D8E2"
  white4: "#E1E5EF"
  white3: "#EAEDF6"
  white2: "#F4F6FB"
  white1: "#FFFFFF"

  # Mushroom
  ## Icon
  mush-icon-border-radius: 12px
  mush-chip-border-radius: 12px
  mush-chip-icon-size: 0.5em

  # Card-Mod
  card-mod-theme: Filikun Theme Rounded
 
  card-mod-view-yaml: |

    hui-masonry-view:
      $: |

        /* Swipe-card full width on mobile */

        @media screen and (max-width: 599px) {
          #columns .column swipe-card {
            margin-left: -4px;
            margin-right: -4px;
          }
        }

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
      /* desktop */
      @media screen and (min-width: 800px) {
        #root {
          grid-template-columns: 390px;
        }
      }     

  card-mod-root-yaml: |

    ha-tabs$: |
      @media screen and (max-width: 800px) {    
        #tabsContent {
          width: 97%;
          height: 44px;
        }
      }
    .: |
      @media screen and (max-width: 800px) { 
        @media (orientation: portrait) {
          a.menu-link[target="_blank"], ha-button-menu, ha-menu-button, [main-title] {
            display: none !important;
          } 
          .toolbar {
            padding-right: 0px;
            padding-left: 0px;           
          }
        }
      }
      /* phone */
      @media screen and (max-width: 800px) {      
        .header {
          display: none;
      }
      /* phone */
      @media screen and (max-width: 800px) {              
        .toolbar {
          display: none;
        }
      }
      @media screen and (max-width: 800px) { 
        #view {
          min-height: 100% !important;
          margin-top: -10px !important;
        }
      }
      @media screen and (max-width: 800px) { 
        ha-tabs {
          --paper-tabs-selection-bar-color: var(--header-tab-indicator-color) !important;
          --mdc-icon-size: 28px;
        }
      }
      @media screen and (max-width: 800px) { 
        paper-tab[aria-selected=true] {
          color: var(--header-active-tab-color) !important;
        }
      }
      @media screen and (max-width: 800px) { 
        paper-tab {
          padding-left: 0px;
          padding-right: 0px;
          width: calc(100% / 3);
          color: var(--header-all-tabs-color) !important;
        }
      }       

  card-mod-card-yaml: |

    .: |

      /* General changes */ 

      ha-card {
        transition: none !important;
        font-family: 'Roboto', sans-serif !important;
      }

      /* Graph card style */

      .graph {
        background: var(--blue-tint);
        display: flex;
        overflow: hidden; /* Temporary fix for graph overflow bug */
      }
      
      .graph .name {
        font-size: 12px;
        line-height: 18px;
        background: var(--black);
        color: var(--white);
        padding: 6px 10px;
        border-radius: 100px;
        z-index: 1;
      }

      .graph .icon {
        display: none;
      }

      .graph .info {
        margin-top: 0;
        padding: 24px 24px 0 24px;
        order: 1;
      }

      .graph hui-graph-header-footer {
        order: 3;
      }

      .graph .header {
        padding: 0 24px;
        order: 2;
        margin: 4px 0 -16px 0;
        z-index: 1;
      }

  modes:
    light:
      # Black white contrats
      contrast1: var(--white1)
      contrast2: var(--white2)
      contrast3: var(--white3)
      contrast4: var(--white4)
      contrast5: var(--white5)
      contrast6: var(--white6)
      contrast7: var(--white7)
      contrast8: var(--white8)
      contrast9: var(--white9)
      contrast10: var(--white10)
      contrast11: var(--black10)
      contrast12: var(--black9)
      contrast13: var(--black8)
      contrast14: var(--black7)
      contrast15: var(--black6)
      contrast16: var(--black5)
      contrast17: var(--black4)
      contrast18: var(--black3)
      contrast19: var(--black2)
      contrast20: var(--black1)
      # Color tint transparancy
      color-tint: "0.20"
      # Contrast RGB variables
      contrast1-RGB: 255,255,255

      # Progress bar
      progress-bar: 0, 0, 0     
      # Buttons
      paper-item-icon-active-color: var(--primary-color)
      # States and Badges
      state-icon-active-color: var(--paper-item-icon-active-color)
      state-icon-unavailable-color: var(--disabled-text-color)
      # Labels
      label-badge-background-color: rgb(248, 250, 249)
      label-badge-text-color: var(--primary-text-color)
      label-badge-red: rgb(199, 72, 76)
      label-badge-green: rgb(109, 192, 113)
      label-badge-blue: rgb(26, 115, 232)
      label-badge-yellow: rgb(217, 183, 87)
      label-badge-gray: rgb(95, 98, 103)
      # Dropdowns
      material-background-color: var(--card-background-color)
      material-secondary-background-color: var(--primary-background-color)
      mdc-theme-surface: var(--primary-background-color)
      # Pre/Code
      markdown-code-background-color: rgb(242, 242, 242)
      code-editor-background-color: rgb(242, 242, 242)
      # Checkboxes
      mdc-checkbox-unchecked-color: rgb(191, 191, 191)
      mdc-checkbox-disable-color: var(--disabled-text-color)
      mdc-select-fill-color: rgb(245, 245, 245)
      mdc-select-ink-color: var(--primary-text-color)
      mdc-select-label-ink-color: var(--secondary-text-color)
      mdc-select-idle-line-color: var(--primary-text-color)
      mdc-select-dropdown-icon-color: var(--secondary-text-color)
      mdc-select-hover-line-color: var(--accent-color)
      #RGB
      rgb-primary-text-color: 32, 33, 36
      rgb-primary-color: 32, 33, 36
      rgb-accent-color: 26, 115, 232
      rgb-state-switch-color: var(--rgb-accent-color)
      rgb-state-light-color: var(--rgb-accent-color)
      rgb-state-fan-color: var(--rgb-accent-color)
      rgb-state-script-color: var(--rgb-accent-color)
      rgb-state-vacuum-color: var(--rgb-accent-color)
      rgb-state-remote-color: var(--rgb-accent-color)
      rgb-state-input-boolean-color: var(--rgb-accent-color)
      rgb-state-humidifier-color: var(--rgb-accent-color)
      rgb-state-cover-color: var(--rgb-accent-color)

    dark:
      # Black white contrats
      contrast1: var(--black1)
      contrast2: var(--black2)
      contrast3: var(--black3)
      contrast4: var(--black4)
      contrast5: var(--black5)
      contrast6: var(--black6)
      contrast7: var(--black7)
      contrast8: var(--black8)
      contrast9: var(--black9)
      contrast10: var(--black10)
      contrast11: var(--white10)
      contrast12: var(--white9)
      contrast13: var(--white8)
      contrast14: var(--white7)
      contrast15: var(--white6)
      contrast16: var(--white5)
      contrast17: var(--white4)
      contrast18: var(--white3)
      contrast19: var(--white2)
      contrast20: var(--white1)
      # Color tint transparancy
      color-tint: "0.15"
      # Contrast RGB variables
      contrast1-RGB: 0,0,0

      # Progress bar
      progress-bar: 255, 255, 255
      # Buttons
      paper-item-icon-active-color: rgb(138, 180, 248)
      # States and Badges
      state-icon-active-color: var(--paper-item-icon-active-color)
      state-icon-unavailable-color: var(--disabled-text-color)

      # Labels
      label-badge-background-color: var(--secondary-background-color)
      label-badge-text-color: var(--primary-text-color)
      label-badge-red: rgb(208, 101, 104)
      label-badge-green: rgb(128, 200, 132)
      label-badge-blue: rgb(138, 180, 248)
      label-badge-yellow: rgb(223, 194, 113)
      label-badge-gray: rgb(95, 98, 103)

      # Dropdowns
      material-background-color: var(--table-row-background-color)
      material-secondary-background-color: var(--table-row-alternative-background-color)
      mdc-theme-surface: var(--secondary-background-color)
      # Pre/Code
      markdown-code-background-color: rgb(23, 23, 23)
      code-editor-background-color: rgb(23, 23, 23)      
      # Checkboxes
      mdc-checkbox-unchecked-color: rgb(169, 177, 188)
      mdc-checkbox-disable-color: var(--disabled-text-color)
      mdc-select-fill-color: rgb(42, 43, 46)
      mdc-select-ink-color: var(--primary-text-color)
      mdc-select-label-ink-color: var(--secondary-text-color)
      mdc-select-idle-line-color: var(--primary-text-color)
      mdc-select-dropdown-icon-color: var(--secondary-text-color)
      mdc-select-hover-line-color: var(--accent-color)
      mdc-text-field-fill-color: var(--mdc-select-fill-color)      

      #RGB
      rgb-primary-text-color: 169, 177, 188
      rgb-primary-color: 169, 177, 188
      rgb-accent-color: 138, 180, 248
      rgb-state-switch-color: var(--rgb-accent-color)
      rgb-state-light-color: var(--rgb-accent-color)
      rgb-state-fan-color: var(--rgb-accent-color)
      rgb-state-script-color: var(--rgb-accent-color)
      rgb-state-vacuum-color: var(--rgb-accent-color)
      rgb-state-remote-color: var(--rgb-accent-color)
      rgb-state-input-boolean-color: var(--rgb-accent-color)
      rgb-state-humidifier-color: var(--rgb-accent-color)
      rgb-state-cover-color: var(--rgb-accent-color)
```