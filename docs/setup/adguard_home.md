---
layout: default
title: 🏴󠁲󠁵󠁡󠁤󠁿 Adguard
parent: ⚙️ Setup
nav_order: 45
---
# Adguard home

## Get Adguard to display device names

Networks -> WAN
Primary DNS = 1.1.1.1
Secondary DNS = 1.0.0.1
Networks -> LAN
Primary DNS = RPi local network location
Secondary DNS= 1.1.1.1 (see #2 response below)
Adguard home DNS = Unifi USG local network address


For those wanting that, all I did was add the router IP to the DNS Upstream setting within Adgaurd. In addition to doing the changes above.
