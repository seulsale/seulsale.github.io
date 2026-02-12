---
title: ''
summary: ''
date: 2026-02-10
type: landing

design:
  spacing: '0'

sections:
  # Hero Section
  - block: dev-hero
    id: hero
    content:
      username: me
      greeting: "Hi, I'm"
      show_status: true
      show_scroll_indicator: true
      typewriter:
        enable: true
        prefix: "I build"
        strings:
          - "automation for IBM Z"
          - "homelab infrastructure"
          - "open source tools"
          - "CI/CD pipelines"
        type_speed: 70
        delete_speed: 40
        pause_time: 2500
      cta_buttons:
        - text: View My Work
          url: "#projects"
          icon: arrow-down
        - text: Get In Touch
          url: "#contact"
          icon: envelope
    design:
      style: centered
      avatar_shape: circle
      animations: true
      background:
        color:
          light: "#ffffff"
          dark: "#0a0a0f"
      spacing:
        padding: ["6rem", "0", "4rem", "0"]

  # Tech Stack
  - block: tech-stack
    id: skills
    content:
      title: "Tech Stack"
      subtitle: "Technologies I work with daily"
      categories:
        - name: Automation
          items:
            - name: Ansible
              icon: devicon/ansible
            - name: Terraform
              icon: devicon/terraform
            - name: GitHub Actions
              icon: brands/github
        - name: Languages
          items:
            - name: Python
              icon: devicon/python
            - name: Go
              icon: devicon/go
            - name: Bash
              icon: devicon/bash
        - name: Platforms
          items:
            - name: Linux
              icon: devicon/linux
            - name: IBM Z
              icon: hero/server
            - name: RHEL
              icon: devicon/redhat
        - name: Infrastructure
          items:
            - name: Docker
              icon: devicon/docker
            - name: Kubernetes
              icon: devicon/kubernetes
            - name: Proxmox
              icon: hero/server-stack
    design:
      style: grid
      show_levels: false
      background:
        color:
          light: "#f0f4f3"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  # Experience Timeline
  - block: resume-experience
    id: experience
    content:
      title: Experience
      date_format: Jan 2006
      items:
        - title: Software Developer
          company: IBM
          company_url: 'https://www.ibm.com'
          company_logo: ''
          location: Austin, TX
          date_start: '2022-03-01'
          date_end: ''
          description: |2-
            * Contributing to the Ansible for IBM Z ecosystem, building collections and modules that automate z/OS operations
            * Collaborating with cross-functional teams to modernize mainframe workflows through infrastructure as code
            * Mentoring junior developers on Ansible best practices and z/OS automation patterns
            * Shipped 3 major Ansible collection releases used by Fortune 500 enterprises
        - title: Systems Engineer
          company: Acme Cloud Solutions
          company_url: 'https://example.com'
          company_logo: ''
          location: Remote
          date_start: '2020-06-01'
          date_end: '2022-02-28'
          description: |2-
            * Designed and maintained CI/CD pipelines for hybrid cloud deployments across AWS and on-prem
            * Automated infrastructure provisioning using Terraform and Ansible for 200+ servers
            * Reduced deployment time by 60% through pipeline optimization and parallelization
            * Implemented monitoring stack with Prometheus, Grafana, and custom alerting
        - title: DevOps Intern
          company: Lorem Tech Inc.
          company_url: 'https://example.com'
          company_logo: ''
          location: San Francisco, CA
          date_start: '2019-06-01'
          date_end: '2019-08-31'
          description: |2-
            * Built monitoring dashboards with Grafana and Prometheus for microservices fleet
            * Wrote Python scripts to automate log analysis and reduce MTTR by 30%
            * Contributed to internal Ansible roles for developer environment provisioning
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  # Projects
  - block: portfolio
    id: projects
    content:
      title: "Projects"
      subtitle: "Side projects and things I've built"
      count: 0
      filters:
        folders:
          - projects
      buttons:
        - name: All
          tag: '*'
        - name: Ansible
          tag: Ansible
        - name: Homelab
          tag: Homelab
        - name: Python
          tag: Python
      default_button_index: 0
    design:
      columns: 3
      background:
        color:
          light: "#f0f4f3"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  # Homelab Services
  - block: markdown
    id: services
    content:
      title: "Homelab Services"
      subtitle: "Self-hosted on a multi-node Proxmox cluster, managed with Ansible"
      text: |-
        <div class="services-grid">
          <a href="https://pve.lab.seulsale.com" target="_blank" rel="noopener" class="service-card">
            <div class="service-icon">&#9881;</div>
            <div class="service-info">
              <h4>Proxmox VE</h4>
              <p>Virtualization cluster &mdash; 3 nodes, 96 GB RAM</p>
            </div>
          </a>
          <a href="https://git.seulsale.com" target="_blank" rel="noopener" class="service-card">
            <div class="service-icon">&#128193;</div>
            <div class="service-info">
              <h4>Gitea</h4>
              <p>Self-hosted Git with CI runners</p>
            </div>
          </a>
          <a href="https://grafana.seulsale.com" target="_blank" rel="noopener" class="service-card">
            <div class="service-icon">&#128200;</div>
            <div class="service-info">
              <h4>Grafana</h4>
              <p>Monitoring dashboards &amp; alerting</p>
            </div>
          </a>
          <a href="https://media.seulsale.com" target="_blank" rel="noopener" class="service-card">
            <div class="service-icon">&#127909;</div>
            <div class="service-info">
              <h4>Jellyfin</h4>
              <p>Media server with hardware transcoding</p>
            </div>
          </a>
          <a href="https://ha.seulsale.com" target="_blank" rel="noopener" class="service-card">
            <div class="service-icon">&#127968;</div>
            <div class="service-info">
              <h4>Home Assistant</h4>
              <p>Home automation hub &mdash; 40+ devices</p>
            </div>
          </a>
          <a href="https://dns.seulsale.com" target="_blank" rel="noopener" class="service-card">
            <div class="service-icon">&#128737;</div>
            <div class="service-info">
              <h4>Pi-hole</h4>
              <p>Network-wide DNS ad blocking</p>
            </div>
          </a>
          <div class="service-card">
            <div class="service-icon">&#128274;</div>
            <div class="service-info">
              <h4>Tailscale</h4>
              <p>Mesh VPN connecting all nodes</p>
            </div>
          </div>
          <div class="service-card">
            <div class="service-icon">&#128256;</div>
            <div class="service-info">
              <h4>Traefik</h4>
              <p>Reverse proxy with automatic TLS</p>
            </div>
          </div>
        </div>
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  # Contact
  - block: contact-info
    id: contact
    content:
      title: Get In Touch
      subtitle: "Let's connect"
      text: |-
        I'm always happy to chat about automation, homelab setups, open source,
        or potential collaboration opportunities. Feel free to reach out!
      email: sergio@example.com
      autolink: true
    design:
      columns: '1'
      background:
        color:
          light: "#f0f4f3"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  # CTA
  - block: cta-card
    content:
      title: "Open to Opportunities"
      text: |-
        Interested in working together? I'm always open to discussing **automation engineering**,
        **DevOps**, or **infrastructure** roles.
      button:
        text: 'View My LinkedIn'
        url: https://www.linkedin.com/in/seulsale/
        new_tab: true
    design:
      card:
        css_class: 'bg-gradient-to-br from-primary-200 via-primary-100 to-secondary-200 dark:from-primary-600 dark:via-primary-700 dark:to-secondary-700'
        text_color: dark
      background:
        color:
          light: "#ffffff"
          dark: "#0a0a0f"
      spacing:
        padding: ["4rem", "0", "6rem", "0"]
---
