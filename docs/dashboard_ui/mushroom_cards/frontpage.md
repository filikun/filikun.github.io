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

## Conditional cards
Red alert that a smoke detector is on. Will highlight where and what it has detected (smoke/heat). Blue alerts for ex thunder and if any door or window is open.

<details markdown="block">
  <summary>Image</summary>
![greeter](\assets\images\frontpage\conditional_smoke_detector.png)
</details>
<details markdown="block">
  <summary>Smoke detector</summary>
{% raw %}

```yml
type: vertical-stack
cards:
  - type: conditional
    conditions:
      - entity: group.alert_smoke_and_heat
        state: 'on'
    card:
      type: custom:mushroom-template-card
      primary: Brandvarnare aktiv!
      secondary: >
        {% set fire_alarm = states   | selectattr('entity_id','in',
        state_attr('group.alert_smoke_and_heat','entity_id'))   |
        selectattr('state','eq','on')   | map(attribute='name')   | list %}  {%
        if fire_alarm | length == 0 %} false  {% elif fire_alarm | length == 1
        %} Upptäckt {{  fire_alarm | join('')
          | regex_replace(find='fire alarm bedroom heat', replace='värme i sovrum', ignorecase=true)
          | regex_replace(find='fire alarm bedroom smoke', replace='rök i sovrum', ignorecase=true)
          | regex_replace(find='fire alarm hallway heat', replace='värme i hall', ignorecase=true)
          | regex_replace(find='fire alarm hallway smoke', replace='rök i hall', ignorecase=true)
          }}
        {% else %}  Upptäckt {{  fire_alarm[:-1] | join(', ')
          | regex_replace(find='fire alarm bedroom heat', replace='värme i sovrum', ignorecase=true)
          | regex_replace(find='fire alarm bedroom smoke', replace='rök i sovrum', ignorecase=true)
          | regex_replace(find='fire alarm hallway heat', replace='värme i hall', ignorecase=true)
          | regex_replace(find='fire alarm hallway smoke', replace='rök i hall', ignorecase=true)
          }} {{'' if  fire_alarm | length > 2 else ', '}}och {{  fire_alarm[-1]
          | regex_replace(find='fire alarm bedroom heat', replace='värme i sovrum', ignorecase=true)
          | regex_replace(find='fire alarm bedroom smoke', replace='rök i sovrum', ignorecase=true)
          | regex_replace(find='fire alarm hallway heat', replace='värme i hall', ignorecase=true)
          | regex_replace(find='fire alarm hallway smoke', replace='rök i hall', ignorecase=true)
          }} 
        {% endif %}
      icon: mdi:fire
      icon_color: none
      style: |
        ha-card {
          background: rgba(255.0, 69.0, 58.0, 1.0);
          color: rgba(255.0, 255.0, 255.0, 1.0);
          --secondary-text-color: rgba(255.0, 255.0, 255.0, 1.0);
          }
```
{% endraw %}
</details>

<details markdown="block">
  <summary>Image</summary>
![greeter](\assets\images\frontpage\conditional_thunder.png)
</details>
<details markdown="block">
  <summary>Thunder</summary>
{% raw %}

```yml
type: conditional
conditions:
  - entity: sensor.blitzortung_lightning_counter
    state_not: '0'
card:
  type: custom:mushroom-template-card
  primary: Det åskar!
  secondary: >-
    {{ states('sensor.blitzortung_lightning_counter') }} nedslag senaste
    timmen
  icon: mdi:weather-lightning
  icon_color: none
  style: |
    ha-card {
      background: rgba(10.0, 132.0, 255.0, 1.0);
      color: rgba(255.0, 255.0, 255.0, 1.0);
      --secondary-text-color: rgba(255.0, 255.0, 255.0, 1.0);
      }
```
{% endraw %}
</details>

<details markdown="block">
  <summary>Image</summary>
![greeter](\assets\images\frontpage\conditional_door_window.png)
</details>
<details markdown="block">
  <summary>Door or window open</summary>
{% raw %}

```yml
type: conditional
conditions:
  - entity: group.magnet_doors_and_windows
    state: 'on'
card:
  type: custom:mushroom-template-card
  primary: >
    {% set magnet_doors_and_windows = states   |
    selectattr('entity_id','in',
    state_attr('group.magnet_doors_and_windows','entity_id'))   |
    selectattr('state','eq','on')   | map(attribute='name')   | list %}  {%
    if magnet_doors_and_windows | length == 0 %} false  {% elif
    magnet_doors_and_windows | length == 1 %}
      Öppet i {{  magnet_doors_and_windows | join('')
      | regex_replace(find='Window office magnet contact', replace='kontor', ignorecase=true)
      | regex_replace(find='Window bathroom magnet contact', replace='badrum', ignorecase=true)
      | regex_replace(find='Window bedroom magnet contact', replace='sovrum', ignorecase=true)
      | regex_replace(find='Door outdoor magnet contact', replace='hall(dörr)', ignorecase=true)
      }}
    {% else %} 
      Öppet i {{  magnet_doors_and_windows[:-1] | join(', ')
      | regex_replace(find='Window office magnet contact', replace='kontor', ignorecase=true)
      | regex_replace(find='Window bathroom magnet contact', replace='badrum', ignorecase=true)
      | regex_replace(find='Window bedroom magnet contact', replace='sovrum', ignorecase=true)
      | regex_replace(find='Door outdoor magnet contact', replace='hall(dörr)', ignorecase=true)
      }} {{'' if  magnet_doors_and_windows | length > 1 else ', '}}och {{  magnet_doors_and_windows[-1]
      | regex_replace(find='Window office magnet contact', replace='kontor', ignorecase=true)
      | regex_replace(find='Window bathroom magnet contact', replace='badrum', ignorecase=true)
      | regex_replace(find='Window bedroom magnet contact', replace='sovrum', ignorecase=true)
      | regex_replace(find='Door outdoor magnet contact', replace='hall(dörr)', ignorecase=true)
      }}
    {% endif %}
  secondary: null
  icon: mdi:door-open
  icon_color: none
  style: |
    ha-card {
      background: rgba(10.0, 132.0, 255.0, 1.0);
      color: rgba(255.0, 255.0, 255.0, 1.0);
      --secondary-text-color: rgba(255.0, 255.0, 255.0, 1.0);
      }
```
{% endraw %}
</details>

<details markdown="block">
  <summary>Image</summary>
![greeter](\assets\images\frontpage\conditional_away.png)
</details>
<details markdown="block">
  <summary>Away</summary>
{% raw %}

```yml
type: conditional
conditions:
  - entity: group.presence_family
    state: not_home
card:
  type: custom:stack-in-card
  mode: vertical
  styles:
    '--chip-box-shadow': none
    '--chip-background': none
    '--chip-spacing': 0
  cards:
    - type: custom:mushroom-template-card
      icon: ios:car-fill
      layout: vertical
      tap_action:
        action: more-info
      hold_action:
        action: none
      double_tap_action:
        action: none
      multiline_secondary: false
      primary: Ingen hemma
      secondary: >
        {%- set time = (as_timestamp(now()) -
        as_timestamp(states.group.presence_family.last_changed)) | int  %} {%-
        set minutes = ((time % 3600) // 60) %} {%- set minutes =
        '{}m'.format(minutes) if minutes > 0 else '' %} {%- set hours = ((time %
        86400) // 3600) %} {%- set hours = '{}h '.format(hours) if hours > 0
        else '' %} {%- set days = (time // 86400) %} {%- set days = '{}d
        '.format(days) if days > 0 else '' %} Sedan {{ 'Mindre än en minut
        sedan' if time < 60 else days + hours + minutes }}
      icon_color: blue
    - type: custom:mushroom-chips-card
      chips:
        - type: template
          content: |-
            {% if states('group.magnet_all_windows') == 'on' %}
            Öppen
            {% else  %}
            Stängd
            {% endif %}
          icon: |-
            {% if states('group.magnet_all_windows') == 'on' %}
            mdi:window-open
            {% else  %}
            mdi:window-closed
            {% endif %}
          icon_color: |-
            {% if states('group.magnet_all_windows') == 'on' %}
            pink
            {% else  %}
            none
            {% endif %}
        - type: template
          content: |-
            {% if states('group.magnet_all_doors') == 'on' %}
            Öppen
            {% else  %}
            Stängd
            {% endif %}
          icon: |-
            {% if states('group.magnet_all_doors') == 'on' %}
            mdi:door-open
            {% else  %}
            mdi:door-closed
            {% endif %}
          icon_color: |-
            {% if states('group.magnet_all_doors') == 'on' %}
            pink
            {% else  %}
            none
            {% endif %}
      alignment: center
    - type: custom:mushroom-chips-card
      chips:
        - type: template
          content: >-
            {% if states('group.presence_indoor') == 'on' %}
            Rörelse i {{ states('sensor.presence_last_motion') }} nu
            {% else  %}
            Rörelse i {{ states('sensor.presence_last_motion') }} för   {{
            relative_time(states.sensor.presence_last_motion.last_changed) 
              | replace("hour", "timme") 
              | replace("hours", "timmar") 
              | replace("minute", "minut") 
              | replace("minuts", "minuter") 
              | replace("second", "sekund") 
              | replace("seconds", "sekunder") }} sedan
            {% endif %}
          icon: |-
            {% if states('group.presence_indoor') == 'on' %}
            mdi:motion-sensor
            {% else  %}
            mdi:motion-sensor-off
            {% endif %}
          icon_color: |-
            {% if states('group.presence_indoor') == 'on' %}
            pink
            {% else  %}
            none
            {% endif %}
      alignment: center
```
{% endraw %}
</details>

<details markdown="block">
  <summary>Image</summary>
![greeter](\assets\images\frontpage\conditional_night_mode.png)
</details>
<details markdown="block">
  <summary>Night mode</summary>
{% raw %}

```yml
type: custom:state-switch
entity: template
template: >
  {% if now().hour > 20 or now().hour < 8 %} on {% elif
  states('input_boolean.night_mode') == 'on' %} on {% else %} off {% endif %}
states:
  'on':
    type: custom:mushroom-entity-card
    entity: input_boolean.night_mode
    icon_color: indigo
    icon: ios:moon-stars-fill
    tap_action:
      action: toggle

```
{% endraw %}
</details>

<details markdown="block">
  <summary>Image</summary>
![greeter](\assets\images\frontpage\conditional_guest_mode.png)
</details>
<details markdown="block">
  <summary>Guest mode</summary>
{% raw %}

```yml
type: conditional
conditions:
  - entity: group.presence_guests
    state_not: home
card:
  type: vertical-stack
  cards:
    - type: custom:mushroom-title-card
      title: ''
      subtitle: Gäster
    - type: custom:mushroom-entity-card
      entity: input_boolean.guest_mode
      name: Gäster för natten?
      tap_action:
        action: toggle


```
{% endraw %}
</details>


<table>
  <tr>
    <td width="33%" valign="bottom">
<img alt="Greeter" src="\assets\images\frontpage\greeter.png"><br/>
Greeter</td>
    <td width="33%" valign="bottom">
<img width="50%" alt="Climate chip" src="\assets\images\frontpage\chip_climate.png"/><br/>
Climate chip</td>
    <td width="33%" valign="bottom">
<img alt="Presence" src="\assets\images\frontpage\presence.png"/><br/>
Presence</td>
  </tr>
  <tr>
    <td width="33%" valign="bottom">
<img alt="Presence popup" src="\assets\images\frontpage\presence_popup.png"/><br/>
Presence popup</td>
    <td width="33%" valign="bottom">
<img alt="Conditional smoke detector" src="\assets\images\frontpage\conditional_smoke_detector.png"/><br/>
Conditional smoke detector</td>
    <td width="33%" valign="bottom"><img alt="Conditional thunder" src="\assets\images\frontpage\conditional_thunder.png"/><br/>
Conditional thunder</td>
  </tr>
  <tr>
    <td width="33%" valign="bottom">
<img alt="Conditional door window" src="\assets\images\frontpage\conditional_door_window.png"/><br/>
Conditional door window</td>
    <td width="33%" valign="bottom">
<img alt="Conditional Away" src="\assets\images\frontpage\conditional_away.png"/><br/>
Conditional Away</td>
    <td width="33%" valign="bottom"><img alt="Conditional night mode" src="\assets\images\frontpage\conditional_night_mode.png"/><br/>
Conditional night mode</td>
  </tr>
  <tr>
    <td width="33%" valign="bottom">
<img alt="Conditional guest mode" src="\assets\images\frontpage\conditional_guest_mode.png"/><br/>
Conditional guest mode</td>
  </tr>      
</table>