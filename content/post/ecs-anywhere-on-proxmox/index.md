---
title: "Running AWS ECS Anywhere on a Proxmox Homelab"
subtitle: "Cloud-native orchestration, on-prem hardware, zero EC2 bill"
summary: "How I run production SaaS workloads on ECS Anywhere inside a Proxmox VM — getting AWS's control plane, ECR, and deployment tooling while the compute lives in my house."
date: 2026-07-04
tags:
  - Homelab
  - AWS
  - Proxmox
  - Docker
featured: false
---

My side projects need real infrastructure — APIs, scheduled scrapers, background workers — but paying for EC2 to run workloads that fit comfortably on hardware I already own never sat right with me. ECS Anywhere is the compromise I settled on: AWS owns the control plane, my Proxmox server owns the compute.

## The setup

The homelab runs Proxmox VE on a 12-core, 32 GB machine. One VM is dedicated to ECS: it runs the `amazon-ecs-agent` registered as an *external instance* in a regular ECS cluster. From the AWS console it looks like any other container instance — task definitions, services, deployments, CloudWatch — but the tasks execute at home.

Registration is a one-time SSM activation:

```bash
aws ssm create-activation --iam-role ecsAnywhereRole
curl -o ecs-anywhere-install.sh https://amazon-ecs-agent.s3.amazonaws.com/ecs-anywhere-install-latest.sh
sudo bash ecs-anywhere-install.sh \
  --cluster homelab \
  --activation-id "$ACTIVATION_ID" \
  --activation-code "$ACTIVATION_CODE" \
  --region us-east-1
```

After that, deploying to my house is identical to deploying to Fargate: push an image to ECR, update the task definition, and the agent pulls and swaps containers. My CI pipeline doesn't know or care that the target is a VM under my desk.

## What runs on it

Right now the external instance runs the production API and scraper for [Qanto](https://qan.to), my personal finance app. The scraper is exactly the kind of workload this shines for: long-running, bursty, and completely indifferent to latency — but expensive to keep on a cloud instance 24/7.

## The honest trade-offs

- **You are the datacenter.** Power outage, ISP hiccup, dead disk — that's your pager. I mitigate with Proxmox snapshots and a monitoring VM (Prometheus + Grafana + Loki) that alerts me before users notice.
- **ECS Anywhere still costs money** — about $0.01/hour per registered instance. For one instance that's ~$7/month, far below the EC2 equivalent for the same cores and RAM.
- **No ALB integration on-prem.** Ingress is my own problem; I solve it with Cloudflare Tunnel, which also means zero open ports on my router.

## Why not just Docker Compose?

I ran plain Compose for years. What ECS Anywhere buys me is the deployment story: immutable task definitions, rollbacks, the same `aws ecs update-service` muscle memory I use professionally, and one console showing every environment. The homelab stopped being a snowflake and became just another cluster.
