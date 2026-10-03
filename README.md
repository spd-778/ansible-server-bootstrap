# Ansible Server Bootstrap

Ansible-based server bootstrap project for automating the initial configuration, security hardening, and Docker setup of Linux servers.

The project uses an Ansible inventory to define target servers and reusable roles to apply common system configuration, security settings, and Docker installation.

---

## 📌 Project Overview

This project demonstrates how Ansible can be used to automate server provisioning and configuration management.

Instead of manually configuring each server, the playbook applies a consistent configuration across all machines in the `servers` inventory group.

### Key Objectives

- Automate initial server configuration
- Apply common system settings
- Improve server security
- Install and configure Docker
- Use reusable Ansible roles
- Manage multiple servers through inventory
- Reduce manual server administration

---

## 🏗️ Project Architecture

```text
                         Ansible Control Node
                                  │
                                  │ SSH
                                  ▼
                         ┌─────────────────┐
                         │    Inventory    │
                         │     servers     │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │   playbook.yml  │
                         └────────┬────────┘
                                  │
                 ┌────────────────┼────────────────┐
                 │                │                │
                 ▼                ▼                ▼
          ┌────────────┐   ┌────────────┐   ┌────────────┐
          │   common   │   │  security  │   │   docker   │
          │    role    │   │    role    │   │    role    │
          └────────────┘   └────────────┘   └────────────┘
                 │                │                │
                 └────────────────┼────────────────┘
                                  ▼
                         Configured Servers
