---
title: Ansible Z Collection
date: 2025-06-15
summary: Open-source Ansible collection providing 20+ modules for automating z/OS system administration, job submission, dataset management, and USS operations.
tags:
  - Ansible
  - Automation
  - IBM Z
  - Open Source
links:
  - type: github
    url: https://github.com/seulsale/ansible-z-collection
    label: Code
  - type: live
    url: https://galaxy.ansible.com/seulsale/zos
    label: Ansible Galaxy
featured: true
---

An open-source Ansible collection that provides 20+ modules for automating z/OS system administration tasks. Supports job submission, dataset management, USS file operations, and RACF security configuration.

## Key Features

- **Job Management** - Submit JCL, monitor job status, and retrieve output programmatically
- **Dataset Operations** - Create, copy, delete, and manage MVS datasets with idempotent modules
- **USS Integration** - Full support for Unix System Services file and process management
- **RACF Automation** - Manage users, groups, and permissions through Ansible playbooks

Built with Python and tested against z/OS 2.4+ environments. Used in production by several enterprise teams for automated provisioning and compliance enforcement.
