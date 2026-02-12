---
title: Dotfiles
date: 2024-08-10
summary: Personal dotfiles managed with GNU Stow and Ansible. Neovim, tmux, zsh, and system configuration for Fedora and macOS workstations.
tags:
  - Linux
  - Ansible
  - Automation
links:
  - type: github
    url: https://github.com/seulsale/dotfiles
    label: Code
featured: true
---

Personal configuration files and system setup automation. Uses GNU Stow for symlinking and an Ansible playbook for bootstrapping new machines from scratch.

## Included Configs

- **Neovim** - LSP, Treesitter, telescope, custom keybindings
- **tmux** - Status bar, session management, vim-like navigation
- **zsh** - Starship prompt, custom aliases, fzf integration
- **Git** - Global config, commit templates, diff tools
- **Ansible bootstrap** - One-command setup for Fedora or macOS
