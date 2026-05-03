---
title: "Building My Own Home Server for MVP Development"
description: "How I built a low-cost home server using an Intel N100 mini PC and Proxmox to run startup MVPs, pilot applications, and personal projects"
author: "Vijay Kumar G"
authorImage: "@/images/blog/vijay.jpg"
authorImageAlt: "Avatar Description"
pubDate: 2026-05-04
cardImage: "@/images/blog/post-4.png"
cardImageAlt: "Home server setup with Intel N100 mini PC running Proxmox"
readTime: 5
tags: ["self-hosting", "homelab", "proxmox", "devops", "docker", "automation"]
---

I wanted to build and test real web applications without burning money on cloud bills or VPS subscriptions.

So instead of renting infrastructure, I built my own low-cost home server.

What started as a self-hosting hobby quickly became a practical platform for running startup MVPs, pilot applications, and personal projects, all from a tiny Intel N100 mini PC.

## My Setup

- Intel N100 Mini PC (16GB RAM)
- Proxmox installed instead of Windows
- Lightweight LXC containers for:
  - PostgreSQL database
  - Multiple backend services
  - Multiple frontend services
  - HAProxy reverse proxy
  - Prometheus + Grafana monitoring
  - [WUD](https://getwud.github.io/wud/#/) for automated Docker image updates
  - [Home Assistant](https://www.home-assistant.io/) for IoT and home automation

## Why This Setup Works

My priorities were simple:

- Low cost
- Low power consumption
- Simplicity
- Automation

This mini PC runs on just a 12V (2.5A) power supply, making it extremely efficient and easy to back up with an affordable router UPS (Li-ion battery) during power outages.

## Public Hosting from Home

I requested a static public IP from my ISP, forwarded ports 80/443, and configured HAProxy for:

- Domain-based routing
- Reverse proxying
- TLS termination
- Let's Encrypt SSL certificates
- Basic security protections

This means I can securely host multiple applications from home, just like a lightweight private cloud.

## Automation = The Real Game Changer

Every code push to GitHub can:

- Build new Docker images
- Publish them automatically
- Let WUD detect updates
- Deploy the latest version to my home server

So theoretically: Idea → Code → PR → Merge → Live deployment from my own infrastructure.

That's incredibly powerful for rapid MVP experimentation.

## Current Resource Usage

Even with multiple web apps, a monitoring stack, reverse proxy, database, and home automation running, my system usually stays around:

- 1–3% CPU
- ~20% RAM

Which means I still have massive room to scale.

## Why I Love This Approach

For a relatively small upfront investment and minimal monthly costs, I now have:

- My own development cloud
- Pilot deployment infrastructure
- Full control
- Better learning
- Lower recurring costs
- A playground for future projects

## What's Next?

- Automated database backups
- More applications
- Continued expansion of my personal private cloud

For developers, indie hackers, or self-hosting enthusiasts: you don't always need expensive cloud infrastructure to start building seriously.

Sometimes, a small low-power machine at home is more than enough.
