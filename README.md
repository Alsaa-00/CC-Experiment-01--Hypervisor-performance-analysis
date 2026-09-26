# Cloud Computing Lab

# Performance Analysis of Type-1 and Type-2 Hypervisors

## Proxmox VE (Type-1) vs VMware Workstation (Type-2)

---

## 1. Introduction

A hypervisor is a software or firmware layer that enables virtualization
and allows multiple virtual machines to run on physical computing
resources.

Hypervisors are broadly classified into two types:

- Type-1 Hypervisor – Bare-metal hypervisor
- Type-2 Hypervisor – Hosted hypervisor

This experiment performs a practical performance analysis of a Type-1
hypervisor and a Type-2 hypervisor using identically configured Ubuntu
virtual machines.

The two platforms used are:

- Proxmox VE – Type-1 Hypervisor
- VMware Workstation – Type-2 Hypervisor

CPU performance is measured using Sysbench.

---

# 2. Aim

To analyze and compare the CPU performance of Type-1 and Type-2
hypervisors using identically configured virtual machines and the
Sysbench CPU benchmark.

---

# 3. Objectives

- To understand virtualization and hypervisors.
- To study Type-1 and Type-2 hypervisors.
- To configure an Ubuntu virtual machine on Proxmox VE.
- To configure an Ubuntu virtual machine on VMware Workstation.
- To maintain similar VM configurations for both environments.
- To verify CPU, memory, disk, and system configuration.
- To install and use Sysbench.
- To perform CPU performance benchmarking.
- To record benchmark measurements.
- To analyze the performance results.
- To compare the results obtained from both hypervisors.
- To visualize the benchmark results using graphs.

---

# 4. Requirements

## Hardware / Environment

- Computer system
- Network connectivity
- Proxmox VE server
- VMware Workstation
- Ubuntu ISO image

## Software

- Proxmox VE
- VMware Workstation
- Ubuntu
- Sysbench
- Web browser

---

# 5. Virtual Machine Configuration

Both virtual machines should use the same basic configuration so that
the performance comparison is performed under comparable conditions.

| Resource | Configuration |
|---|---|
| Guest Operating System | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB |
| Disk | 20 GB |
| CPU Benchmark | Sysbench |
| Benchmark Parameter | cpu-max-prime=20000 |

---

# 6. Hypervisor Classification

## 6.1 Type-1 Hypervisor

A Type-1 hypervisor is also known as a bare-metal hypervisor.

It operates directly on the physical server hardware and manages virtual
machines and their allocated resources.

### Type-1 Hypervisor Used

**Proxmox VE**

---

## 6.2 Type-2 Hypervisor

A Type-2 hypervisor is also known as a hosted hypervisor.

It runs on top of an existing host operating system and provides an
environment for creating and running virtual machines.

### Type-2 Hypervisor Used

**VMware Workstation**

---

# 7. Type-1 Hypervisor – Proxmox VE

## Part A: Performance Analysis Using Proxmox VE

Proxmox VE is used as the Type-1 hypervisor.

The Ubuntu virtual machine is created with:

- 2 vCPU
- 2 GB RAM
- 20 GB disk
- Ubuntu operating system

The VM is then verified and benchmarked using Sysbench.

---

## 7.1 Accessing Proxmox VE

The Proxmox VE web interface is accessed using:

```text
https://<PROXMOX_SERVER_IP>:8006

