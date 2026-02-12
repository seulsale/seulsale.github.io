---
title: Homelab IaC
date: 2025-04-01
summary: Infrastructure as code repository for my entire homelab - Proxmox cluster provisioning, Docker Compose stacks, Ansible playbooks, and automated backups.
tags:
  - Homelab
  - Docker
  - Ansible
  - Linux
links:
  - type: github
    url: https://github.com/seulsale/homelab-iac
    label: Code
featured: true
---

Complete infrastructure as code setup for a multi-node Proxmox homelab. Everything from VM provisioning to service deployment is automated and version controlled.

## Architecture

- **3-node Proxmox cluster** with Ceph storage (12TB usable)
- **20+ Docker containers** managed via Compose with Ansible deployment
- **Traefik** reverse proxy with automatic Let's Encrypt certificates
- **Tailscale** mesh VPN for secure remote access
- **Automated backups** to Backblaze B2 with restic

## Services Deployed

Media stack (Jellyfin, Sonarr, Radarr), productivity (Gitea, Nextcloud), monitoring (Grafana, Prometheus, Loki), networking (Pi-hole, Traefik), and home automation (Home Assistant, Zigbee2MQTT).

All configuration is managed through Ansible roles with encrypted secrets via ansible-vault.
