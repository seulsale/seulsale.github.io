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
      greeting: "Hey, I'm"
      show_status: true
      show_scroll_indicator: true
      typewriter:
        enable: true
        prefix: "I build"
        strings:
          - "SaaS products from scratch"
          - "enterprise migration platforms"
          - "automation for everything"
          - "homelab infrastructure"
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
        - name: Languages
          items:
            - name: Python
              icon: devicon/python
            - name: JavaScript
              icon: devicon/javascript
            - name: TypeScript
              icon: devicon/typescript
            - name: Bash
              icon: devicon/bash
        - name: Backend
          items:
            - name: Django
              icon: devicon/django
            - name: FastAPI
              icon: devicon/fastapi
            - name: Node.js
              icon: devicon/nodejs
        - name: Frontend
          items:
            - name: React
              icon: devicon/react
            - name: Next.js
              icon: devicon/nextjs
        - name: Cloud & Infrastructure
          items:
            - name: Azure
              icon: devicon/azure
            - name: AWS
              icon: devicon/amazonwebservices
            - name: Docker
              icon: devicon/docker
            - name: Kubernetes
              icon: devicon/kubernetes
            - name: VMware ESXi
              icon: hero/server-stack
        - name: Automation & DevOps
          items:
            - name: Ansible
              icon: devicon/ansible
            - name: GitHub Actions
              icon: brands/github
            - name: Azure DevOps
              icon: devicon/azure
        - name: Platforms
          items:
            - name: Linux
              icon: devicon/linux
            - name: IBM Z
              icon: hero/server
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
        - title: Software Engineer (Contractor)
          company: Enterprise Industrial Clients
          company_url: ''
          company_logo: ''
          location: Saltillo, MX
          date_start: '2026-01-06'
          date_end: ''
          description: |2-
            * Contracting for major automotive companies on platform modernization initiatives
            * Leading legacy-to-modern migrations using Python, React, and Azure (Entra ID, Azure DevOps)
            * Building IoT-integrated systems, data pipelines, and internal tooling with Python and Kubernetes
            * Implementing RBAC access models, modern auth patterns, and cloud-native architectures
            * Collaborating with hardware engineers and manufacturing stakeholders to define migration priorities
        - title: Founder & Full Stack Developer
          company: ClinicNet
          company_url: 'https://clinicnet.app'
          company_logo: ''
          location: Remote
          date_start: '2024-01-01'
          date_end: ''
          description: |2-
            * Built and launched a profitable multi-tenant B2B SaaS serving 120+ paying dental clinics
            * Architected with Django + django-tenants, Next.js frontend, and Stripe subscription billing
            * Integrated WhatsApp Business API for automated appointment reminders
            * Solo developer handling architecture, development, deployment, and customer support
        - title: Advisory Software Engineer
          company: IBM
          company_url: 'https://www.ibm.com'
          company_logo: ''
          location: Remote
          date_start: '2022-02-01'
          date_end: '2025-11-30'
          description: |2-
            * Contributed to the Ansible for IBM Z ecosystem, building automation for mainframe environments
            * Led DevSecOps migration initiatives across 7+ enterprise teams
            * Delivered technical workshops and demos to Fortune 500 clients
            * Developed internal platforms and tooling used across multiple teams
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  # Education
  - block: resume-education
    id: education
    content:
      title: Education
      date_format: Jan 2006
      items:
        - title: Computer Systems Engineering
          institution: Instituto Tecnológico de Saltillo
          date_start: ''
          date_end: '2021-01-01'
          description: ''
    design:
      columns: '1'
      background:
        color:
          light: "#f0f4f3"
          dark: "#08080c"
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
        - name: SaaS
          tag: SaaS
        - name: Python
          tag: Python
        - name: Homelab
          tag: Homelab
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
      subtitle: "Self-hosted infrastructure managed with Docker and Ansible"
      text: |-
        <div class="services-grid">
          <div class="service-card">
            <div class="service-icon">&#9881;</div>
            <div class="service-info">
              <h4>VMware ESXi</h4>
              <p>Bare-metal hypervisor</p>
            </div>
          </div>
          <div class="service-card">
            <div class="service-icon">&#128230;</div>
            <div class="service-info">
              <h4>Docker</h4>
              <p>Container orchestration</p>
            </div>
          </div>
          <div class="service-card">
            <div class="service-icon">&#128274;</div>
            <div class="service-info">
              <h4>Tailscale</h4>
              <p>Mesh VPN</p>
            </div>
          </div>
          <div class="service-card">
            <div class="service-icon">&#127968;</div>
            <div class="service-info">
              <h4>Home Assistant</h4>
              <p>Home automation</p>
            </div>
          </div>
          <a href="https://ollama.seulsale.com" target="_blank" rel="noopener" class="service-card">
            <div class="service-icon">&#129504;</div>
            <div class="service-info">
              <h4>Ollama</h4>
              <p>Self-hosted LLM inference</p>
            </div>
          </a>
          <div class="service-card">
            <div class="service-icon">&#9729;</div>
            <div class="service-info">
              <h4>AWS ECS Anywhere</h4>
              <p>Hybrid cloud container orchestration</p>
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
        I'm always happy to chat about SaaS, automation, homelab setups,
        or potential collaboration opportunities. Feel free to reach out!
      email: contact@seulsale.com
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
        Interested in working together? I'm always open to discussing **software engineering**,
        **full-stack development**, or **platform modernization** opportunities.
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
