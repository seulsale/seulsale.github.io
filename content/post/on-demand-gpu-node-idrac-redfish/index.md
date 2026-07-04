---
title: "Powering a GPU Node On-Demand with iDRAC and Redfish"
subtitle: "A Dell R630 that sleeps until I need LLM inference"
summary: "A rack server with a GPU is great for self-hosted LLMs and terrible for a power bill. Here's the tiny Redfish-based tooling I use to boot it on demand and shut it down when I'm done."
date: 2026-07-04
tags:
  - Homelab
  - Automation
  - LLM
  - Bash
featured: false
---

There's a Dell PowerEdge R630 in my homelab whose only job is GPU work — mainly [Ollama](https://ollama.com) for self-hosted LLM inference. Rack servers are power-hungry, and paying to idle one 24/7 for something I use a few hours a week is absurd. So the machine stays **off by default** and boots on demand.

## Redfish: the API your server already has

Every server with a BMC (iDRAC on Dell, iLO on HP) exposes the [Redfish API](https://www.dmtf.org/standards/redfish) — a REST interface to the hardware itself. The BMC draws a couple of watts and is always reachable, even when the host is powered off. Power control is a single POST:

```bash
curl -sk -K ~/.bmc-creds \
  -H 'Content-Type: application/json' \
  -X POST "https://$BMC/redfish/v1/Systems/System.Embedded.1/Actions/ComputerSystem.Reset" \
  -d '{"ResetType": "On"}'
```

Two details worth stealing:

1. **Keep credentials out of `argv`.** Curl's `-K` flag reads options from a file, so the BMC password never shows up in `ps` or shell history. The creds file is `chmod 600`, owned by root.
2. **`GracefulShutdown` first, `ForceOff` as the escape hatch.** Redfish supports both; the graceful path lets the OS unmount cleanly.

I wrapped this in a ~40-line script (`esxi up | down | status`) that also queries `PowerState`, so any machine on my VPN can check or change the server's state in one command.

## Making it a button

CLI is fine at a desk, but the whole point is "I want to ask a model something *now*." So the script is wired into a small dashboard on my hypervisor — one page showing every service's health, with **Power on / Shut down** buttons for the GPU node. Boot to Ollama-ready takes about four minutes; the dashboard's status dot flips green when the tunnel to it comes back up.

The pattern generalizes to anything with a BMC:

- **State** lives in the BMC, not the OS — you can always trust it.
- **Actions** are idempotent Redfish POSTs — safe to put behind a button.
- **Health** is best checked end-to-end — I probe the actual Ollama endpoint, not just a ping.

## The economics

An R630 idles around 90–120 W. At my rates, leaving it on costs roughly $10–15/month to do nothing; on-demand it's pennies. The four-minute boot is a fair trade for inference that runs on my hardware, on my network, with no tokens metered by anyone.
