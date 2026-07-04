---
title: "Zero Open Ports: Publishing Homelab Services with Cloudflare Tunnel"
subtitle: "Public URLs for self-hosted services without touching the router"
summary: "Every public service in my homelab — Grafana, static sites, LLM inference — is reachable over HTTPS without a single forwarded port. Here's the ingress architecture and what I'd do differently."
date: 2026-03-15
tags:
  - Homelab
  - Security
  - Cloudflare
  - Networking
featured: false
---

Port forwarding is how homelabs get owned. Every forwarded port is a doorbell on the public internet, ringing straight into your house, answered by whatever software you last remembered to patch. My rule for the homelab is simple: **zero open inbound ports**, ever.

## How the traffic flows

[Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/) inverts the connection. A lightweight daemon (`cloudflared`) runs inside the network and dials *out* to Cloudflare's edge. Public hostnames — `grafana.example.com`, `monitor.example.com` — are DNS records pointing at the tunnel, and Cloudflare routes each one to an internal address the daemon can reach:

```yaml
ingress:
  - hostname: grafana.example.com
    service: http://monitoring-vm:3000
  - hostname: sites.example.com
    service: http://caddy:80
  - service: http_status:404   # explicit default: drop everything else
```

The router does nothing. There is nothing to scan. From outside, my house looks like a device that never answers.

## The layers, in order

1. **Cloudflare edge** — TLS termination, DDoS absorption, and the only surface an attacker can see.
2. **The tunnel** — outbound-only; a connector VM runs `cloudflared` as a systemd service, and a second connector runs in Docker for a separate domain serving static sites through Caddy.
3. **The service's own auth** — everything published still has a login (Grafana, Beszel, the Proxmox UI). A tunnel hides the network, not a weak password.
4. **Everything else stays private** — admin surfaces I don't need public (the control dashboard, SSH to most machines) live only on Tailscale, the overlay VPN layered across every node.

For the services that should be *really* private — SSH in particular — Cloudflare Access sits in front of the tunnel hostname, requiring an identity check before the connection ever reaches my network.

## Lessons learned

- **End the ingress list with an explicit 404.** The default catch-all is the difference between "I exposed three services" and "I exposed whatever happened to respond."
- **One tunnel per trust domain.** My personal-brand services and my throwaway static sites run on separate tunnels with separate credentials; a leaked token compromises one, not both.
- **Auth-gated is not the same as private.** A public login page is still public. If you wouldn't want the URL in a search index, put it behind Access or keep it VPN-only.
- **Monitor from inside.** Blackbox-exporter probes both the internal address and the public hostname, so I can tell "service is down" apart from "tunnel is down" at a glance in Grafana.

The result: friends reach the Minecraft server, recruiters reach my dashboards, and my router's port-forwarding table has been empty for a year.
