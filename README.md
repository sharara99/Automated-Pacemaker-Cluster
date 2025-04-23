# 🛠️ High Availability Web Cluster with Pacemaker, Corosync, Apache, iSCSI, and SBD

## 📘 Overview

This project presents a **fully configured High Availability (HA) Web Cluster** built using enterprise-level open-source tools on three CentOS VMs: `serverA`, `serverB`, and `serverC`. The cluster ensures **continuous service availability**, **automated failover**, and **node fencing** using **SBD (Storage-Based Death)**.

It showcases how to:

- Design a fault-tolerant infrastructure
- Implement automated service failover
- Use iSCSI as shared fencing storage
- Deploy Apache across nodes with a shared dynamic web app

---

## 🧱 Project Components

| Component | Description |
| --- | --- |
| **Pacemaker** | Cluster Resource Manager – handles starting/stopping resources |
| **Corosync** | Messaging layer – ensures node membership and communication |
| **PCS** | CLI tool to configure and manage clusters |
| **Apache (httpd)** | Web server used to host a PHP-based dynamic page |
| **NFS** | Network File System for shared website files across nodes |
| **SBD** | Watchdog-based fencing tool using a shared disk to ensure split-brain prevention |
| **iSCSI** | Used to create a shared block storage device between nodes for fencing |
| **Virtual IP (VIP)** | Shared floating IP that ensures client traffic always reaches the active node |

---

## 🎯 Project Goals

- ✅ **Achieve High Availability**: Ensure the service remains available even if one or two nodes fail.
- ✅ **Fencing via SBD**: Avoid split-brain scenarios by isolating unresponsive nodes.
- ✅ **Shared Web Content**: Ensure consistent content using NFS across all web servers.
- ✅ **Dynamic Node Detection**: Web page shows which node is actively serving traffic.
- ✅ **Auto Failover**: Automatically relocate VIP and Apache to a healthy node on failure.

---

## 🧠 Architecture Diagram

![Animation.gif](attachment:d0e05b12-0964-480b-ab7c-2d9fc13f0df3:Animation.gif)
