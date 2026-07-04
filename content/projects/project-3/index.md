---
title: Hybrid Cloud Homelab
date: 2025-04-01
summary: "Self-hosted infrastructure on Proxmox VE running AWS ECS Anywhere clusters on local hardware, blending cloud-native orchestration with on-prem servers. Hosts a full observability stack (Grafana, Prometheus, Loki), containerized services, and automated deployments — all published through Cloudflare Tunnel with zero open ports."
tags:
  - Homelab
  - Proxmox
  - AWS ECS
  - Docker
  - Hybrid Cloud
links:
  - type: live
    url: https://grafana.seulsale.com
    label: Grafana
  - type: live
    url: https://monitor.seulsale.com
    label: Beszel
featured: true
---

Self-hosted infrastructure on Proxmox VE running AWS ECS Anywhere clusters on local hardware, blending cloud-native orchestration with on-prem servers. Hosts a full observability stack, containerized services, and automated deployments — all published through Cloudflare Tunnel with zero open ports.

## Stack

- **Proxmox VE** - Bare-metal hypervisor managing dedicated VMs for services, ingress, and monitoring
- **AWS ECS Anywhere** - Hybrid cloud container orchestration running production SaaS workloads on local hardware
- **Docker** - Container runtime for all self-hosted services
- **Grafana + Prometheus + Loki** - Metrics, logs, and alerting across the whole fleet, plus Beszel for lightweight per-host monitoring
- **Ollama** - LLM inference on a GPU node (Dell R630) powered on-demand via iDRAC Redfish automation
- **Pi-hole** - Network-wide DNS ad blocking
- **Caddy** - Static site hosting behind Cloudflare Tunnel
- **Cloudflare Tunnel + Tailscale** - Zero-trust ingress and mesh VPN for secure remote access, with no ports exposed to the internet
- **Ansible** - Configuration management and automated deployments
