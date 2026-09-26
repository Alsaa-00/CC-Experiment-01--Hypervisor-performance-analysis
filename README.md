# Cloud Computing Lab

## Performance Analysis of Type-1 and Type-2 Hypervisors

### Proxmox VE vs VMware Workstation

---

## 1. Introduction

A hypervisor is a software layer that enables virtualization by allowing
multiple virtual machines (VMs) to run on a physical computer.

Each virtual machine can have its own operating system, virtual CPU,
memory, storage, and network resources.

Hypervisors are broadly classified into two types:

1. Type-1 Hypervisor
2. Type-2 Hypervisor

This experiment studies the performance of both types of hypervisors by
running similarly configured Ubuntu virtual machines and measuring their
CPU performance using Sysbench.

---

# 2. Aim

To analyze and compare the performance of Type-1 and Type-2 hypervisors
using identical virtual machine configurations and a CPU benchmark.

The hypervisors considered in this experiment are:

- Type-1: Proxmox VE
- Type-2: VMware Workstation

---
## 2.1. Repository Structure

```text
CC-Experiment-01-Hypervisor-Analysis/
│
├── README.md
├── LAB_REPORT.md
│
├── Results/
│   └── Performance-analysis.md
│
├── Graphs/
│   ├── execution-time-comparison.png
│   ├── events-per-second-comparison.png
│   ├── average-latency-comparison.png
│   ├── latency-comparison.png
│   └── overall-performance-comparison.png
│
└── Screenshots/
    ├── Comparison/
    ├── Type - 02 VMware/
    └── Type-01 proxmox/

# 3. Objectives

The main objectives of this experiment are:

- To understand the concept of virtualization.
- To understand Type-1 and Type-2 hypervisors.
- To configure virtual machines with identical resources.
- To deploy Ubuntu on both virtualization platforms.
- To monitor the virtual machine configurations and resources.
- To perform CPU benchmarking using Sysbench.
- To record the benchmark results.
- To compare the performance of the two hypervisor environments.
- To understand the effect of the virtualization layer on VM performance.

---

# 4. Virtualization

Virtualization is a technology that allows physical computing resources
such as CPU, memory, storage, and networking to be divided and presented
as virtual resources.

A virtual machine behaves like an independent computer and can run its
own operating system and applications.

Virtualization provides:

- Resource isolation
- Efficient resource utilization
- Multiple operating systems on one physical machine
- Easier testing and development
- Flexible resource allocation
- Simplified deployment and management

---

# 5. Hypervisor

A hypervisor, also called a Virtual Machine Monitor (VMM), is a software
or firmware layer responsible for creating and managing virtual machines.

The hypervisor manages the physical hardware resources and allocates
virtual resources to individual virtual machines.

The major resources managed by a hypervisor include:

- CPU
- RAM
- Storage
- Network interfaces

Hypervisors are classified into Type-1 and Type-2 based on where the
hypervisor operates in relation to the host operating system.

---

# 6. Type-1 Hypervisor

A Type-1 hypervisor is also called a **bare-metal hypervisor**.

It runs directly on the physical hardware instead of running on top of
a conventional host operating system.

The virtual machines are managed directly by the hypervisor layer.

### Characteristics

- Runs directly on physical hardware.
- Does not require a conventional host operating system underneath it.
- Provides virtualization and resource management directly.
- Commonly used in servers and data centers.
- Provides an environment designed specifically for virtualization.

### Type-1 Hypervisor Used

**Proxmox VE**

Proxmox Virtual Environment (Proxmox VE) is the Type-1 virtualization
platform used in this experiment.

---

# 7. Type-2 Hypervisor

A Type-2 hypervisor is also called a **hosted hypervisor**.

It runs as an application on top of an existing host operating system.

The host operating system manages the physical hardware while the
hypervisor provides the virtualization environment for virtual machines.

### Characteristics

- Runs on top of a host operating system.
- Uses the host operating system to access physical resources.
- Commonly used for desktop virtualization, development, testing,
  and educational environments.
- Provides a convenient environment for running virtual machines on
  personal computers.

### Type-2 Hypervisor Used

**VMware Workstation**

VMware Workstation is the Type-2 virtualization platform used in this
experiment.

---

# 8. Type-1 vs Type-2 Hypervisor

| Feature | Type-1 Hypervisor | Type-2 Hypervisor |
|---|---|---|
| Other Name | Bare-metal hypervisor | Hosted hypervisor |
| Location | Runs directly on hardware | Runs on a host operating system |
| Example Used | Proxmox VE | VMware Workstation |
| Host OS Dependency | Does not require a conventional host OS | Requires a host operating system |
| Typical Usage | Servers and data centers | Desktop, development and testing |
| Virtual Machines | Managed directly by the hypervisor | Managed through the host OS and hypervisor |

---

# 9. Proxmox VE

Proxmox VE is the Type-1 virtualization platform used for the experiment.

The virtual machine is created inside the Proxmox environment with the
specified hardware configuration.

The Ubuntu virtual machine is then used for system verification and
benchmarking.

The Proxmox VM configuration used in this experiment includes:

- Operating System: Ubuntu
- CPU: 2 vCPU
- Memory: 2048 MB
- Storage: 20 GB

---

# 10. VMware Workstation

VMware Workstation is the Type-2 virtualization platform used for the
second part of the experiment.

The Ubuntu virtual machine is created inside VMware Workstation using
the same basic resource configuration as the Proxmox virtual machine.

The VMware VM configuration used in this experiment includes:

- Operating System: Ubuntu
- CPU: 2 vCPU
- Memory: 2048 MB
- Storage: 20 GB

Using similar configurations allows the benchmark results from the two
environments to be compared under controlled conditions.

---

# 11. Experimental Configuration

To make the comparison meaningful, the virtual machines are configured
with the same resources.

### Standard VM Configuration

| Resource | Configuration |
|---|---|
| Operating System | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB |
| Storage | 20 GB |
| CPU Benchmark | Sysbench |

The same CPU benchmark is executed inside both virtual machines.

---

# 12. System Verification

Before running the benchmark, the Ubuntu virtual machines are checked
to verify their system configuration.

The following commands are used for verification:

```bash
hostnamectl

# 18. Performance Analysis Graphs

The performance of the Type-1 and Type-2 hypervisors will be analyzed
using the actual Sysbench benchmark results obtained from both
environments.

The following graphs will be used for comparison:

## 18.1 Execution Time Comparison

This graph compares the total CPU benchmark execution time of:

- Proxmox VE
- VMware Workstation

**Graph:**

`graphs/execution-time-comparison.png`

---

## 18.2 Events Per Second Comparison

This graph compares the number of benchmark events processed per second
by the two hypervisor environments.

**Graph:**

`graphs/events-per-second-comparison.png`

---

## 18.3 Average Latency Comparison

This graph compares the average CPU benchmark latency between:

- Proxmox VE
- VMware Workstation

**Graph:**

`graphs/average-latency-comparison.png`

---

## 18.4 Minimum and Maximum Latency Comparison

This graph compares the minimum and maximum latency recorded during the
Sysbench benchmark.

**Graph:**

`graphs/latency-comparison.png`

---

## 18.5 Overall Performance Comparison

A final graph will summarize the measured performance parameters of both
hypervisor environments.

**Graph:**

`graphs/overall-performance-comparison.png`

> The graphs will be added after the actual benchmark results are
> collected. No estimated or fabricated values will be used.

