---
layout: default
title: 🔗 Remote access
parent: ⚙️ Setup
nav_order: 21
---
# Remote access

## Cloudflare and Nginx Proxy manager

Buy/move a domain on/to Cloudflare. In the DNS tab set up your `A` records where `name` is subdomain and `content` is your public IP address. Make sure `proxy statu`s is checked on.

In the SSL/TLS tab set encryption mode to `Full (strict)` and move over to the `Origin Server` subtab. Click to create a new certificate. Private key type should be `RSA (2048)` and list the hostnames you want to use. In my case it's `*.domain.xyz` and `domain.xyz` as I wan't to include all possible subdomains. Certificate validity should be set to `15 years`. Click create.

On your deskop make two files named `origin.pem` and `privkey.pem` and copy and paste the content from Cloudflare into these files.

In Nginx proxy manager, move to the SSL Certificates tab and click Add SSL Certificate -&gt; Custom. Name it however you like and choose `privkey.pem` as your `Certificate Key` and `origin.pem` as your `Certificate` and hit save.

Now you can add new proxy hosts in Nginx and use your new Cloudflare SSL certificate, make sure to enable `Force SSL`.

## Unfi firewall setup

As an extra layer of protection we can make sure that our firewall only responds to Cloudflare's proxy IP addresses. Making an firewall rule would be ideal but for some reason the USG does not allow us to set a firewall rule that simultaneous open ports for us. The solution is to use a Port Forwarding rule for every cloudflare proxy IP (Yes it sucks),

In the Unifi controller, move over to the settings -&gt; Firewall &amp; Security tab. Click Create New Port Forwarding and name it whatever you like (CF 1 &gt; HA).

[Here is the list of cloudflare proxy IP's](https://www.cloudflare.com/ips-v4)

```
Name: CF 1 > HA
Enable Forwarding Rule: Enabled
From: Limited
Source: Cloudflare proxy IP
Port: 443
Forward IP: Nginx proxy manager IP address
Forward Port: 443
Protocol: TCP

Save and repeat
```

### If your using Adguard or Pihole

Make sure to utilize DNS rewrites. Move to `Filters -> DNS rewrites` and `Add DNS rewrite`. Domain is whatever domain your using in cloudflare ex `subdomain.domain.xyz` and in the second field you put the IP address of the service you want it to point to.