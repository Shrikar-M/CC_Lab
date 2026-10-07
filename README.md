# ☁️ Cloud Computing Lab

## ✨ Project Overview

This repository documents a Cloud Computing laboratory experiment in which an Ubuntu virtual machine was configured and tested on two different hypervisor platforms.

The practical work covers **virtual machine provisioning, guest system verification, resource monitoring, and CPU performance benchmarking using Sysbench**.

| Lab | Platform | What the Screenshots Document |
|---|---|---|
| Part A · Type-1 | Proxmox VE / KVM | VM setup, running guest, Ubuntu system checks, resource monitoring, and Sysbench output |
| Part B · Type-2 | VMware Workstation | VM configuration, Ubuntu system checks, Sysbench installation, and benchmark output |

---

## 🎯 Aim

To compare the CPU performance of a **Type-1 hypervisor (Proxmox VE)** and a **Type-2 hypervisor (VMware Workstation)** by running similarly configured Ubuntu virtual machines and executing the same Sysbench CPU benchmark on both platforms.

---

## 📌 Objectives

- Create an Ubuntu virtual machine on Proxmox VE (Type-1).
- Create an Ubuntu virtual machine with similar resources on VMware Workstation (Type-2).
- Verify the guest operating system and system resources.
- Run the Sysbench CPU benchmark on both virtual machines.
- Record total execution time, total events, events per second, and latency.
- Compare the measured performance of both hypervisor configurations.
- Analyze the difference in benchmark results.
- Store screenshots and experiment documentation in a GitHub repository.

---

# 🖥️ Hypervisor Performance Analysis

## Type-1 vs Type-2 Hypervisor Comparison

### Proxmox VE (Type-1) vs VMware Workstation (Type-2)

---

## 🔍 What is This Experiment?

This experiment compares two different types of hypervisors.

A **hypervisor** is software or a virtualization layer that allows multiple virtual machines to run on a physical computer.

### Type-1 Hypervisor

A Type-1 hypervisor runs directly on the physical hardware and provides virtualization services to virtual machines.

**Example:** Proxmox VE using KVM-based virtualization.

### Type-2 Hypervisor

A Type-2 hypervisor runs as software on top of a host operating system.

**Example:** VMware Workstation.

In this experiment, an Ubuntu virtual machine was configured on both platforms with similar resources.

The same CPU benchmark was then executed on both virtual machines and the results were compared.

---

# 📊 Recorded Benchmark Results

The following Sysbench command was used:

`sysbench cpu --cpu-max-prime=20000 run`

The recorded benchmark results were:

| Metric | Proxmox VE · Type-1 | VMware Workstation · Type-2 |
|---|---:|---:|
| Events per Second | 1,749.16 | 707.43 |
| Total Events | 17,494 | 7,077 |
| Test Duration | 10.0005 s | 10.0006 s |
| Average Latency | 0.57 ms | 1.41 ms |

### Performance Difference

Based on the recorded events-per-second values:

`(1749.16 - 707.43) / 707.43 × 100 ≈ 147.24%`

Therefore, Proxmox VE achieved approximately **147.24% higher measured throughput** than VMware Workstation in these recorded runs.

Another way to express the difference is:

`1749.16 / 707.43 ≈ 2.47`

Therefore, Proxmox VE achieved approximately **2.47× the measured CPU throughput** of VMware Workstation.

> **Note:** These results represent the specific runs performed during this experiment. They should not be interpreted as a universal ranking of Type-1 and Type-2 hypervisors because CPU scheduling, host-system load, VM configuration, hardware, and run-to-run variation can affect benchmark results.

---

# 🧪 Experiment at a Glance

## Type-1 · Proxmox VE

The Proxmox VE virtual machine was configured with:

- 2 vCPU
- 2 GB RAM
- 20 GB virtual disk
- Ubuntu guest operating system

The screenshots document:

- Proxmox VM configuration
- VM running state
- Ubuntu console
- Guest system configuration
- Sysbench benchmark output
- Resource monitoring

All Proxmox screenshots are stored in:

`screenshots/Type1-proxmox/`

---

## Type-2 · VMware Workstation

The VMware Workstation virtual machine was configured with:

- 2 vCPU
- 2 GB RAM
- 20 GB virtual disk
- Ubuntu guest operating system

The screenshots document:

- VMware VM configuration
- VM running state
- Ubuntu system configuration
- Sysbench installation and benchmark output

All VMware screenshots are stored in:

`screenshots/Type2-vmware/`

---

# 🗂️ Repository Structure

```text
CC_Lab/
│
├── README.md
├── LAB_REPORT.md
│
├── screenshots/
│   ├── Type1-proxmox/
│   │   ├── 01-proxmox-dashboard.png
│   │   ├── 02-proxmox-vm-configuration.png
│   │   ├── 03-proxmox-vm-running.png
│   │   ├── 04-proxmox-ubuntu-console.png
│   │   ├── 05-proxmox-system-configuration.png
│   │   ├── 06-proxmox-sysbench-result.png
│   │   └── 07-proxmox-resource-monitoring.png
│   │
│   ├── Type2-vmware/
│   │   ├── 01-vmware-vm-configuration.jpeg
│   │   ├── 02-vmware-vm-running.jpeg
│   │   ├── 03-vmware-system-configuration.jpeg
│   │   └── 04-vmware-sysbench-result.jpeg
│   │
│   └── comparison/
│       └── 01-hypervisor-performance-comparison.jpeg
│
├── results/
│   └── performance-analysis.md
│
└── .gitkeep
