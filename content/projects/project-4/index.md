---
title: zOS Log Analyzer
date: 2024-11-20
summary: Python CLI tool that parses z/OS syslog and job output, detects anomalies with pattern matching, and sends alerts to Slack or PagerDuty.
tags:
  - Python
  - IBM Z
  - Monitoring
links:
  - type: github
    url: https://github.com/seulsale/zos-log-analyzer
    label: Code
featured: true
---

A Python CLI tool for parsing and analyzing z/OS system logs. Supports syslog, JES2 job output, and SMF records. Uses configurable pattern matching and threshold-based alerting to detect anomalies in mainframe environments.

## Features

- **Multi-format parsing** - Handles syslog, JESMSGLG, JESJCL, and SMF record formats
- **Pattern rules** - YAML-based rule definitions for custom alert conditions
- **Integrations** - Sends notifications to Slack, PagerDuty, or email
- **Dashboard export** - Generates Grafana-compatible JSON for visualization
