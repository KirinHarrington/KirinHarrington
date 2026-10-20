---
title: 'Self-Hosted Homelab'
description: 'A Proxmox and Raspberry Pi homelab running self-hosted services, monitored with Prometheus and Grafana and accessed securely over Tailscale.'
pubDate: 'Oct 19 2026'
tags: ['Proxmox', 'Tailscale', 'Self-hosting', 'Monitoring', 'Home Assistant']
repo: 'https://github.com/yourusername/homelab'
heroImage: '/images/homelab-diagram.svg'
---

## Goal

[1-2 sentences: why you built it. For example: replace cloud services with self-hosted alternatives, learn virtualisation and networking, and practise running and securing real services.]

## Architecture

![Homelab architecture diagram](/images/homelab-diagram.svg)

All devices connect over a Tailscale mesh VPN, so [no services are exposed directly to the internet. Only say this if it is true].

| Host | Role | Services |
|---|---|---|
| HP ProLiant G7 Tower | Proxmox VE hypervisor | Firefly III, Vaultwarden, Immich, Nextcloud, Homepage, Prometheus, Grafana |
| Raspberry Pi 4B | Smart home | Home Assistant with Zigbee dongle, a second shared Home Assistant instance |

[Add how services are run: one VM or LXC container per service, or Docker inside a VM. Mention how many VMs and containers you have.]

## What I built

- **Virtualisation:** [how you set up Proxmox, how services are separated into VMs/LXCs, storage layout]
- **Secure remote access:** Tailscale on [number] devices, including friends' phones. [Mention ACLs/tags if you use them, or what you restrict.]
- **Password and data hosting:** Vaultwarden, Nextcloud and Immich replace cloud equivalents, so my data stays on hardware I control.
- **Monitoring:** Prometheus scrapes metrics from [Proxmox / node exporter / services] and Grafana displays dashboards for [CPU, RAM, disk, uptime].
- **Smart home:** Home Assistant on a Pi with a Zigbee dongle for local control, plus a separate instance that lets friends share location, as a self-hosted alternative to Life360.

## Security decisions

This is the section recruiters will care about most. Fill in what you actually did, and be honest about gaps.

- **Network exposure:** [what is reachable from outside, how Tailscale limits it]
- **Access control:** [Tailscale ACLs, which users/devices reach which services, how friends are restricted to the shared instance only]
- **Authentication:** [2FA on Vaultwarden, Nextcloud and Proxmox, admin account hardening, SSH key-only login]
- **Updates and patching:** [how you update Proxmox, VMs, containers and the Pi]
- **Backups:** [what is backed up, where, how often, whether you have tested a restore]
- **Privacy:** the shared Home Assistant holds friends' location data, so [what consent and access limits you set, who can see what].

## Challenges and what I learned

- [A real problem you hit, how you diagnosed it, how you fixed it]
- [Another one, such as storage, networking, a failed update, or a performance bottleneck]
- [What you would do differently]

## Next steps

- [For example: add a SIEM such as Wazuh, centralised logging with Loki, VLAN segmentation, automated backups, or Fail2ban/CrowdSec]
