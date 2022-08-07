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

![alt text](\assets\images\frontpage\greeter.png)

<details open markdown="block">
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