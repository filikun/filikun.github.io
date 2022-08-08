---
layout: default
title: 📄 Frontpage
parent: 🍄 Mushroom cards
grand_parent: 🦄 Dashboard UI
nav_order: 1
---

# Front page

## Greeter
Will greet the user and change depending on time of day.

<details markdown="block">
  <summary>Image</summary>
![greeter](\assets\images\frontpage\greeter.png)
</details>

<details markdown="block">
  <summary>Code</summary>
{% raw %}
```yml
type: custom:button-card
template: card_header
variables:
  card_header_back_button: false
  card_header_title: |
    [[[
      const d = new Date();
      var hour = d.getHours();
      if (hour <= '6'){
        var greet = 'God natt';
        var emoji = '😴';
      } else if (hour <= '10'){
        var greet = 'God morgon';
        var emoji = '☕';
      } else if (hour <= '12'){
        var greet = 'God dag';
        var emoji = '🙂';
      } else if (hour <= '15'){
        var greet = 'God dag';
        var emoji = '😊';
      } else if (hour <= '18'){
        var greet = 'God dag';
        var emoji = '😎';
      } else if (hour <= '23'){
        var greet = 'God kväll';
        var emoji = '🥱';
      } else {
        var greet = 'God natt';
        var emoji = '😴';
      }
      return greet + ' ' + user.name + '!' + ' ' + emoji;
    ]]]
```
{% endraw %}
</details>

## Chip
Will weather and indoor temperature and humidity average.

<details markdown="block">
  <summary>Image</summary>
![chip_climate](\assets\images\frontpage\chip_climate.png)
</details>

<details markdown="block">
  <summary>Code</summary>
{% raw %}
```yml
type: custom:mushroom-chips-card
chips:
  - type: weather
    entity: weather.smhi_hemma
    show_conditions: true
    show_temperature: true
    tap_action:
      action: navigate
      navigation_path: /lovelace/statistics
  - type: template
    content: >-
      🌡️ {{ states('sensor.temperature_indoor_average')| round(0, 0)  }}°C  •💧
      {{ states('sensor.humidity_indoor_average')| round(0, 0)  }}%
    tap_action:
      action: navigate
      navigation_path: /lovelace/statistics
alignment: center
```
{% endraw %}
</details>


## Presence
Show who is home and not. Popup will show detail on map and phone status (Home/Away wifi/4G, Battery level and adress).

<details markdown="block">
  <summary>Image</summary>
![presence](\assets\images\frontpage\presence.png)
![presence_popup](\assets\images\frontpage\presence_popup.png)
</details>

<details markdown="block">
  <summary>Code</summary>
{% raw %}
```yml
type: template
entity: person.filip
icon: mdi:face-man
icon_color: |-
  {% set connection = states("person.filip")
  %}
  {% if connection == "home" %}
  blue
  {% else %}
  grey
  {% endif %}
content: ''
tap_action:
  action: fire-dom-event
  browser_mod:
    command: popup
    deviceID:
      - this
    title: Filip
    card:
      type: vertical-stack
      cards:
        - type: map
          entities:
            - entity: person.filip
            - entity: zone.home
          default_zoom: 15
          aspect_ratio: '1.5'
          dark_mode: true
          card_mod:
            style:
              ha-map$: |
                .leaflet-control-attribution {
                  visibility: hidden;
                 }
        - type: custom:mushroom-chips-card
          alignment: center
          chips:
            - type: template
              card_mod:
                style: |
                  ha-card {
                    --chip-background: transparent;
                    box-shadow: none;
                  }
              icon: >-
                {% set connection =
                states("sensor.filip_iphone_geocoded_location") %}
                {% if connection == "Hem" %}
                mdi:home
                {% else %}
                mdi:car
                {% endif %}
              entity: sensor.filip_iphone_connection_type
              tap_action:
                action: more-info
            - type: template
              card_mod:
                style: |
                  ha-card {
                    --chip-background: transparent;
                    box-shadow: none;
                  }
              icon: >-
                {% set connection =
                states("sensor.filip_iphone_connection_type") %}
                {% if connection == "Wi-Fi" %}
                mdi:wifi
                {% else %}
                mdi:signal-4g
                {% endif %}
              entity: sensor.filip_iphone_connection_type
              tap_action:
                action: more-info
            - type: template
              card_mod:
                style: |
                  ha-card {
                    --chip-background: transparent;
                    box-shadow: none;
                  }
              content: ''
              icon: >-
                {% set level = states("sensor.filip_iphone_battery_level")|
                int %}
                {% set status = states("sensor.filip_iphone_battery_state")
                %}
                {% if level >= 91 and status == "Full" %}
                mdi:battery
                {% elif level >= 90 and status == "Charging" %}
                mdi:battery-charging-90
                {% elif level >= 80 and status == "Charging" %}
                mdi:battery-charging-80
                {% elif level >= 70 and status == "Charging" %}
                mdi:battery-charging-70
                {% elif level >= 60 and status == "Charging" %}
                mdi:battery-charging-60
                {% elif level >= 50 and status == "Charging" %}
                mdi:battery-charging-50
                {% elif level >= 40 and status == "Charging" %}
                mdi:battery-charging-40
                {% elif level >= 30 and status == "Charging" %}
                mdi:battery-charging-30
                {% elif level >= 20 and status == "Charging" %}
                mdi:battery-charging-20
                {% elif level >= 10 and status == "Charging" %}
                mdi:battery-charging-10
                {% elif level >= 0 and status == "Charging" %}
                mdi:battery-charging-outline
                {% elif level >= 91 %}
                mdi:battery
                {% elif level >= 90 %}
                mdi:battery-90
                {% elif level >= 80 %}
                mdi:battery-80
                {% elif level >= 70 %}
                mdi:battery-70
                {% elif level >= 60 %}
                mdi:battery-60
                {% elif level >= 50 %}
                mdi:battery-50
                {% elif level >= 40 %}
                mdi:battery-40
                {% elif level >= 30 %}
                mdi:battery-30
                {% elif level >= 20 %}
                mdi:battery-20
                {% elif level >= 10 %}
                mdi:battery-10
                {% elif level >= 0 %}
                mdi:battery-alert-variant-outline
                {% else %}
                mdi:battery-remove-outline
                {% endif %}
              entity: sensor.filip_iphone_battery_state
              tap_action:
                action: more-info
        - type: custom:mushroom-chips-card
          alignment: center
          chips:
            - type: template
              card_mod:
                style: |
                  ha-card {
                    --chip-background: transparent;
                    box-shadow: none;
                  }
              content: >-
                {% set location =
                states("sensor.filip_iphone_geocoded_location") %}
                {% if location == "Hem" %}
                Hemma
                {% else %}
                {{ location }}
                {% endif %}
              tap_action:
                action: more-info
        - type: custom:mushroom-title-card
          title: null
      card_mod:
        style: |
          ha-card {
            background-color: var(--card-background-color);
            padding: 0 0px 8px 0;
          }
```
{% endraw %}
</details>