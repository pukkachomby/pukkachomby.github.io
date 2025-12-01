---
title: "Linux Power on macOS"
date: 2025-11-28
tags:
  - "Linux"
  - "macOS"
  - "Docker"
  - "Virtualization"
  - "Networking"
  - "Operating Systems"
  - "Apple"
categories:
  - "Tech"
---

This post explores various methods for connecting to Linux from macOS, including virtualization and remote access. It also covers connecting to macOS from Linux and managing iCloud files.

<!--more-->

## How to Connect
* Users can establish a connection to their Linux machines remotely when located on the same local network, facilitating seamless access and management from other devices within the network.
* For connectivity beyond the local network, Tailscale offers a secure and convenient solution, allowing users to connect to their Linux systems from any location, effectively extending network access on the go.

## Viewing Options
* On macOS, users can utilize the default **Screen Sharing** application to view and interact with their Linux desktop environment, providing a familiar and integrated experience.
* Alternatively, viewing can be achieved using **SPICE**, a display protocol commonly employed with virtual machines, which can be enabled by installing `virt-viewer` via Homebrew on macOS for enhanced performance and features.
* A web-based viewing option is available through noVNC, allowing users to access their Linux desktop directly within the Safari browser without needing additional client software.

## Terminal Only!
* For command-line-centric workflows, a highly effective method involves obtaining a dedicated Linux server and securely connecting to it using SSH (Secure Shell), enabling remote command execution and administration.
* Users can also aim to replicate their preferred Linux terminal environment and configurations within macOS terminal emulators such as iTerm, or similar alternatives, to maintain a consistent and productive command-line experience.

## Docker Options
* Running Linux within a Docker container presents an exceptionally flexible and efficient approach, encapsulating applications and their dependencies in lightweight, portable units.
* Dockerized Linux environments offer versatility, as they can be deployed and executed directly on the local host machine or on a remote server, adapting to various infrastructure setups.
* Examples of Docker Images:
    * For desktop environments, options include images like `linuxserver/webtop` and `consol/rocky-xfce-vnc`, providing full graphical interfaces within containers.
    * KASM offers specialized images for highly containerized desktop environments, such as `kasmweb/desktop` and `linuxserver/kasm`, which are designed for secure and isolated virtual workspaces, with additional resources available for configuration and deployment.
    * Specific applications like Firefox can also be run in isolation using images such as `linuxserver.io/firefox`, ensuring a consistent browsing experience.
* Links:
    * Desktop environments:
        * [WebTop on DockerHub](https://hub.docker.com/r/linuxserver/webtop)
        * [rocky-xfce-vnc on DockerHub](https://hub.docker.com/r/consol/rocky-xfce-vnc)
    * KASM (for containerized desktop environments):
        * [Desktop](https://hub.docker.com/r/kasmweb/desktop)
        * [KASM DockerHub](https://hub.docker.com/r/linuxserver/kasm)
        * [KASM GH](https://github.com/linuxserver/docker-kasm)
        * [compose.yaml info](https://docs.linuxserver.io/images/docker-kasm/#strict-reverse-proxies)

## VM Options
#### Local Virtualization
* Lima provides an excellent solution for virtualizing Linux directly on macOS, offering high performance and a streamlined user experience, making it a highly recommended choice.
* Cheetah serves as another alternative for local virtualization on macOS, though it primarily acts as a wrapper around the native macOS Virtualization.framework, leveraging Apple's built-in capabilities.

#### Network Virtualization
* For a robust network virtualization setup, users can install and configure Proxmox on a dedicated server, which then allows for the creation and management of multiple Linux virtual machines accessible across the network.

## Remote Connections
* Rather than relying on local or network virtualization, an alternative approach involves running Linux on a separate physical computer or dedicated server.
* To access this remote Linux machine, various remote desktop applications can be utilized:
    * **Guacamole** functions as an excellent Remote Desktop Gateway, often deployed via Docker, providing web-based access to multiple remote desktops without needing a client application.
    * **Rustdesk** is another notable remote desktop software solution, offering secure and efficient remote access capabilities, with resources available to guide users through its setup and usage.
* Links:
    * [Guacamole DockerHub](https://hub.docker.com/r/guacamole/guacamole/)
    * [Rustdesk tutorial](https://www.youtube.com/watch?v=EXL8mMUXs88)

## App-Only Approach
* Rather than committing to a complete Linux installation, users can opt for an "App-Only Approach," focusing on selectively running individual favorite Linux applications.
* Many Linux applications may surprisingly run natively on macOS, eliminating the need for virtualization or containerization for those specific tools.
* For applications that do not run natively, or for better isolation and dependency management, running them within a Docker container is a superior alternative to traditional sideloading methods.

## Connecting to macOS from Linux
* When connecting to macOS from a Linux environment, the iCloud web applications provide a surprisingly capable solution for accessing Apple services, though users should be aware that some features may be absent compared to native macOS applications.
* Additionally, **macOS snaps on Linux**, such as the [icloud-for-linux](https://snapcraft.io/icloud-for-linux) package, offer a way to integrate certain macOS functionalities and services directly into a Linux desktop environment.

## Backing up iCloud Files on Linux
#### Rclone
* Rclone is a versatile command-line tool that can be used for transferring data, including iCloud content, to a Linux system.
* However, it is important to note that Rclone's reliability for iCloud specific transfers has been observed to be inconsistent.

#### Photos Backup
* For backing up iCloud photos, **icloud_photos_downloader** provides a CLI-based solution that requires both Docker and Python installations to function, offering granular control over the download process.
* Alternatively, **docker-icloudpd** presents a robust Docker-based solution specifically designed for downloading iCloud photos, simplifying deployment and management through containerization.
* Links:
    * [icloud_photos_downloader](https://github.com/icloud-photos-downloader/icloud_photos_downloader)
    * [docker-icloudpd](https://github.com/boredazfcuk/docker-icloudpd)
