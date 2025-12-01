---
title: "Block The Bad Sites"
date: 2025-11-27
tags:
  - "Internet Safety"
  - "Parental Controls"
  - "Security"
categories:
  - "Family"
  - "Tech"
---

AdGuard DNS helps block ads, trackers, malware, and adult websites.  Their Family protection servers are perfect for keeping kids safe.

<!--more-->

## Best Practices
* The best thing to do is use AdGuard DNS on a device-level
* Adding it on a router level doesn't protect children when they turn on cellular
* Adding it to a browser doesn't protect them if they install another browser

## Two Methods
#### Method 1
* On the child's iPhone, browse to [AdGuard's site](https://adguard-dns.io/en/public-dns.html)
    * Expand `Option 2`
    * Expand `iOS`
    * Select the `Family protection server` radio button
    * Click:
        * `Download configuration profile`
        * `Continue`
        * `Allow`
        * `Close`
        * `X` to close
* In iOS settings:
    * Click `Profile Downloaded`
    * Click `Install`
    * Follow the directions to install
* Verify installation:
    * The installer should bring you to the `VPN & Device Managment` window
    * Under `Configuration Profile`, it should say `AdGuard DNS`
    * To uninstall:
        * Click on `AdGuard DNS` &rarr; `Remove Profile`

#### Method 2
* On the child's iPhone, in iOS Settings:
    * Click `Wi-Fi`
    * Click the `(i)` symbol for the current network
    * Under the `DNS` tab, click `Configure DNS`
    * Select `Manual`
    * Copy and paste the following servers, one by one:
    ```
    94.140.14.15
    94.140.15.16
    2a10:50c0::bad1:ff
    2a10:50c0::bad2:ff
    ```
