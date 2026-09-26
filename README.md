# CC Experiment 01 – Hypervisor Performance Analysis

<p align="center">
  <b>Type-1 vs Type-2 Hypervisor Performance using Sysbench</b><br>
  <sub>Cloud Computing • Ubuntu VM • CPU Benchmarking</sub>
</p>

---

# 1. Introduction

Cloud computing relies heavily on virtualization to efficiently utilize
computing resources. Virtualization allows multiple virtual machines (VMs)
to run on the same physical hardware while maintaining separate operating
environments.

A key component of virtualization is the **hypervisor**, which manages
virtual machines and controls their access to CPU, memory, storage, and
network resources.

In this experiment, the performance of two different hypervisor
architectures is studied:

- **Type-1 Hypervisor – Proxmox VE**
- **Type-2 Hypervisor – VMware Workstation**

Both environments are used to run Ubuntu virtual machines with similar
resource configurations. Their CPU performance is then measured using
Sysbench.

---

# 2. Virtualization

Virtualization is the process of creating a virtual representation of a
physical computing resource.

A virtual machine behaves like an independent computer and can have its own:

- Operating system
- CPU allocation
- Memory
- Storage
- Network interface
- Applications

The physical computer is called the **host**, while the operating system
running inside the virtual machine is called the **guest operating system**.

### Basic Virtualization Architecture

┌─────────────────────────────────────────────┐
│              Physical Hardware              │
├─────────────────────────────────────────────┤
│                  Hypervisor                 │
├──────────────────────┬──────────────────────┤
│      Virtual Machine 1│     Virtual Machine 2│
│      Ubuntu           │     Ubuntu           │
│      CPU / RAM / Disk │     CPU / RAM / Disk │
└──────────────────────┴──────────────────────┘

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

4. Type-1 Hypervisor

A Type-1 hypervisor, also called a bare-metal hypervisor, runs
directly on the physical hardware.

There is no conventional host operating system between the hypervisor and
the hardware.

Architecture
┌─────────────────────────────┐
│       Virtual Machines      │
├─────────────────────────────┤
│       Type-1 Hypervisor     │
│                             │
│        Proxmox VE            │
├─────────────────────────────┤
│       Physical Hardware     │
└─────────────────────────────┘
Characteristics
Runs directly on physical hardware
Provides direct control over hardware resources
Commonly used in servers and data centers
Supports multiple virtual machines
Designed for efficient resource management
Example Used in This Experiment

Proxmox VE is used as the Type-1 virtualization platform.
5. Type-2 Hypervisor

A Type-2 hypervisor, also called a hosted hypervisor, runs as
software on top of an existing host operating system.

The host operating system manages the physical hardware, while the
hypervisor provides virtualization services to the guest virtual machines.

Architecture
┌─────────────────────────────┐
│       Virtual Machine       │
│           Ubuntu            │
├─────────────────────────────┤
│       Type-2 Hypervisor     │
│      VMware Workstation     │
├─────────────────────────────┤
│       Host Operating System │
├─────────────────────────────┤
│       Physical Hardware     │
└─────────────────────────────┘
Characteristics
Runs on top of a host operating system
Easy to install and configure
Commonly used on desktop and laptop computers
Suitable for development, testing, and educational environments
Contains an additional software layer between the VM and hardware

| Resource | Configuration |
|---|---|
| Guest Operating System | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB |
| Disk | 20 GB |
| CPU Benchmark | Sysbench |
| Benchmark Parameter | cpu-max-prime=20000 |

---
6. Type-1 vs Type-2 Hypervisor
Feature	Type-1 Hypervisor	Type-2 Hypervisor
Architecture	Bare-metal	Hosted
Runs on	Physical hardware	Host operating system
Additional OS layer	No	Yes
Example	Proxmox VE	VMware Workstation
Common usage	Servers and data centers	Desktop and development
Resource access	More direct	Through host OS
Management	Usually centralized	Usually desktop-based

The experiment evaluates how these two architectures behave when running a
similar Ubuntu virtual machine workload.

7. Proxmox VE

Proxmox Virtual Environment (VE) is an open-source virtualization
platform designed for managing virtual machines and containers.

For this experiment, Proxmox VE is used to create and run the Ubuntu
virtual machine in a Type-1 virtualization environment.

The Proxmox web interface provides facilities for:

Virtual machine creation
CPU and memory configuration
Storage management
Network configuration
VM monitoring
VM start and shutdown operations

The Proxmox VM is configured with the required CPU, memory, storage, and
network resources before running the benchmark.

8. VMware Workstation

VMware Workstation is a desktop virtualization platform that allows
users to create and run virtual machines on a host operating system.

For this experiment, VMware Workstation is used as the Type-2 hypervisor.

The virtual machine is configured with resources equivalent to the Proxmox
VM so that the CPU benchmark can be performed under similar conditions.
9. Performance Benchmarking

Performance benchmarking is the process of measuring the behavior of a
system under a defined workload.

In this experiment, the CPU performance of both virtual machines is
measured using Sysbench.

The benchmark provides several useful performance measurements, including:

Total execution time
Total number of events
Events per second
Minimum latency
Average latency
Maximum latency
95th percentile latency

These measurements are used to compare the recorded behavior of the two
virtualization environments.
10. Sysbench

Sysbench is a command-line benchmarking tool used to evaluate system
performance.

For this experiment, the CPU benchmark is used.

The benchmark performs CPU calculations using prime-number calculations.

The same workload is executed in both virtual machines using:
</>bash
sysbench cpu --cpu-max-prime=20000 run
11. Experimental Configuration

Both virtual machines are configured using the same basic resources.

Parameter	Configuration
Guest Operating System	Ubuntu
CPU	2 vCPU
Memory	2 GB
Virtual Disk	20 GB
Benchmark	Sysbench CPU
Maximum Prime	20000

Experimental Architecture
                 SAME VM CONFIGURATION
                         │
             ┌───────────┴───────────┐
             │                       │
             ▼                       ▼
       Proxmox VE              VMware Workstation
        Type-1                    Type-2
             │                       │
             ▼                       ▼
        Ubuntu VM                Ubuntu VM
             │                       │
             └───────────┬───────────┘
                         │
                         ▼
                  Sysbench CPU
                         │
                         ▼
              Performance Metrics
                         │
                         ▼
                 Final Comparison

                 12. System Verification

Before running the benchmark, the Ubuntu virtual machines are checked to
verify their system configuration.

The following commands can be used:

Check operating system
hostnamectl
Check CPU configuration
lscpu
Check memory
free -h
Check disk
df -h
Monitor system resources
top

These checks help verify that both virtual machines are configured with
the intended resources before benchmarking.
12. System Verification

Before running the benchmark, the Ubuntu virtual machines are checked to
verify their system configuration.

The following commands can be used:

Check operating system
hostnamectl
Check CPU configuration
lscpu
Check memory
free -h
Check disk
df -h
Monitor system resources
top

These checks help verify that both virtual machines are configured with
the intended resources before benchmarking.

13. Benchmark Procedure

The following procedure is performed for both hypervisor environments.

Step 1 – Install Sysbench
sudo apt update
sudo apt install sysbench -y
Step 2 – Verify Sysbench
sysbench --version
Step 3 – Run the CPU Benchmark
sysbench cpu --cpu-max-prime=20000 run
Step 4 – Record the Results

The following values are recorded from the Sysbench output:

Metric	Description
Total Execution Time	Total time taken by the benchmark
Total Events	Number of completed benchmark events
Events per Second	Number of events processed per second
Minimum Latency	Lowest recorded latency
Average Latency	Average processing latency
Maximum Latency	Highest recorded latency
95th Percentile	Latency value below which approximately 95% of operations fall



Final Comparison
The final comparison screenshot is stored in:

screenshots/comparison/01-hypervisor-performance-comparison.png


<img width="1200" height="896" alt="image" src="https://github.com/user-attachments/assets/cb194ddb-a3bb-4a2b-875f-95e663f3cbca" />








