---
title: Hybrid Cloud Homelab
date: 2025-04-01
summary: "Self-hosted infrastructure running AWS ECS Anywhere clusters on local hardware, blending cloud-native orchestration with on-prem servers. Hosts LLM inference (Ollama), containerized services, and automated deployments across a VMware ESXi + Docker + ECS stack."
tags:
  - AWS ECS
  - VMware ESXi
  - Docker
  - Ollama
  - Hybrid Cloud
links:
  - type: github
    url: https://github.com/seulsale
    label: Code
  - type: live
    url: https://ollama.seulsale.com
    label: Live
featured: true
---

Self-hosted infrastructure running AWS ECS Anywhere clusters on local hardware, blending cloud-native orchestration with on-prem servers. Hosts LLM inference (Ollama), containerized services, and automated deployments across a VMware ESXi + Docker + ECS stack.

## Stack

- **VMware ESXi** - Bare-metal hypervisor for VM management
- **AWS ECS Anywhere** - Hybrid cloud container orchestration across local and cloud resources
- **Docker** - Container runtime for all self-hosted services
- **Ollama** - Self-hosted LLM inference engine
- **Tailscale** - Mesh VPN for secure remote access
