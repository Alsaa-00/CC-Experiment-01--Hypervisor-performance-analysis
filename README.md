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

7.2 Creating the Virtual Machine

The Proxmox VM creation wizard is used to create the virtual machine.

The configuration process includes:

General
   ↓
OS
   ↓
System
   ↓
Disks
   ↓
CPU
   ↓
Memory
   ↓
Network
   ↓
Confirm
7.3 Proxmox VM Configuration
Parameter	Configuration
VM Name	CC-Experiment1-Type1
Operating System	Ubuntu
CPU	2 vCPU
Sockets	1
Cores	2
Memory	2048 MiB
Disk	20 GB
Network Bridge	vmbr0

The VM is then created and started.

7.4 Ubuntu Installation

Ubuntu is installed inside the Proxmox virtual machine.

The general installation process includes:

Select language.
Select Install Ubuntu.
Configure keyboard layout.
Select installation type.
Select the virtual disk.
Configure timezone.
Create the Ubuntu user account.
Complete installation.
Restart the VM.
Log in to Ubuntu.
7.5 System Verification

The following commands are used to verify the virtual machine.

System Information
hostnamectl
CPU Information
lscpu
Memory Information
free -h
Disk Information
df -h
Resource Monitoring
top

Press q to exit top.

7.6 Installing Sysbench

Update the Ubuntu package repository:

sudo apt update

Install Sysbench:

sudo apt install sysbench -y

Verify the installation:

sysbench --version
7.7 CPU Performance Benchmark

Run:

sysbench cpu --cpu-max-prime=20000 run

Record the following values:

Total execution time
Total number of events
Events per second
Minimum latency
Average latency
Maximum latency
7.8 Type-1 Observation Table
Parameter	Observation
Hypervisor	Proxmox VE
Hypervisor Type	Type-1
Guest OS	Ubuntu
CPU Allocation	2 vCPU
Memory Allocation	2 GB
Disk Allocation	20 GB
Total Execution Time	To be recorded
Total Events	To be recorded
Events per Second	To be recorded
Minimum Latency	To be recorded
Average Latency	To be recorded
Maximum Latency	To be recorded
7.8 Type-1 Observation Table
Parameter	Observation
Hypervisor	Proxmox VE
Hypervisor Type	Type-1
Guest OS	Ubuntu
CPU Allocation	2 vCPU
Memory Allocation	2 GB
Disk Allocation	20 GB
Total Execution Time	To be recorded
Total Events	To be recorded
Events per Second	To be recorded
Minimum Latency	To be recorded
Average Latency	To be recorded
Maximum Latency	To be recorded
7.9 Proxmox Resource Monitoring

The Proxmox interface can be used to observe:

CPU usage
Memory usage
Network traffic
Disk usage

The resource observations will be recorded as part of the experiment.

8. Type-2 Hypervisor – VMware Workstation
Part B: Performance Analysis Using VMware Workstation

VMware Workstation is used as the Type-2 hypervisor.

The Ubuntu virtual machine is configured using the same basic resources
as the Proxmox VM.

8.1 Creating the VMware Virtual Machine

Open VMware Workstation and select:

Create a New Virtual Machine

Select:

Typical (recommended)

Select the Ubuntu ISO image as the installation media.

8.2 VMware VM Configuration
Parameter	Configuration
VM Name	CC-Experiment1-Type2
Guest OS	Ubuntu
CPU	2 vCPU
Processors	1
Cores per Processor	2
Memory	2048 MB
Hard Disk	20 GB
Network	NAT
8.3 Ubuntu Installation

Complete the Ubuntu installation inside VMware Workstation.

The installation includes:

Select language.
Select Install Ubuntu.
Configure keyboard layout.
Select installation type.
Configure the virtual disk.
Select timezone.
Create the user account.
Complete installation.
Restart the VM.
Log in to Ubuntu.
8.4 System Verification

Verify the VMware Ubuntu VM using:

hostnamectl

CPU:

lscpu

Memory:

free -h

Disk:

df -h

Resource monitoring:

top

Press q to exit.

8.5 Installing Sysbench

Update the package repository:

sudo apt update

Install Sysbench:

sudo apt install sysbench -y

Verify:

sysbench --version
8.6 CPU Performance Benchmark

Run the same benchmark used in Part A:

sysbench cpu --cpu-max-prime=20000 run

Record:

Total execution time
Total events
Events per second
Minimum latency
Average latency
Maximum latency
8.7 Type-2 Observation Table
Parameter	Observation
Hypervisor	VMware Workstation
Hypervisor Type	Type-2
Guest OS	Ubuntu
CPU Allocation	2 vCPU
Memory Allocation	2 GB
Disk Allocation	20 GB
Total Execution Time	To be recorded
Total Events	To be recorded
Events per Second	To be recorded
Minimum Latency	To be recorded
Average Latency	To be recorded
Maximum Latency	To be recorded
9. Performance Analysis

The performance analysis will be performed using the actual Sysbench
results obtained from both virtual machines.

The following metrics will be analyzed:

Total Execution Time
Total Events
Events Per Second
Minimum Latency
Average Latency
Maximum Latency

The same benchmark configuration is used for both hypervisors.

10. Performance Comparison

The results obtained from Proxmox VE and VMware Workstation will be
compared using the measured benchmark values.

Performance Metric	Proxmox VE	VMware Workstation
Total Execution Time	To be recorded	To be recorded
Total Events	To be recorded	To be recorded
Events Per Second	To be recorded	To be recorded
Minimum Latency	To be recorded	To be recorded
Average Latency	To be recorded	To be recorded
Maximum Latency	To be recorded	To be recorded

The comparison will be based only on the actual measurements obtained
during the experiment.

11. Graphical Analysis

Graphs will be created from the actual benchmark results.

11.1 Execution Time Comparison

A bar graph will compare the total execution time of:

Proxmox VE
VMware Workstation

Graph file:

Graphs/execution-time-comparison.png
11.2 Events Per Second Comparison

A bar graph will compare the events processed per second by both
hypervisor environments.

Graph file:

Graphs/events-per-second-comparison.png
11.3 Average Latency Comparison

A bar graph will compare the average latency measured during the
Sysbench CPU benchmark.

Graph file:

Graphs/average-latency-comparison.png
11.4 Minimum and Maximum Latency Comparison

A comparison graph will display the minimum and maximum latency recorded
for both hypervisors.

Graph file:

Graphs/latency-comparison.png
11.5 Overall Performance Comparison

A final graphical comparison will summarize the measured performance
metrics of Proxmox VE and VMware Workstation.

Graph file:

Graphs/overall-performance-comparison.png

The graphs will be created only from the actual experimental results.
No estimated or fabricated values will be used.

12. Results

The final results will be entered after completing both Part A and
Part B.

The results will contain:

Proxmox VE benchmark output
VMware Workstation benchmark output
Performance comparison table
Graphical comparison
Observations
13. Screenshots

The actual screenshots captured during the experiment will be stored
in the Screenshots directory.

Type-1 – Proxmox VE

Screenshots related to Part A will be stored in:

Screenshots/Type-01 proxmox/

These may include:

Proxmox dashboard
VM configuration
Running VM
Ubuntu console
System configuration
Sysbench result
Resource monitoring
Type-2 – VMware Workstation

Screenshots related to Part B will be stored in:

Screenshots/Type - 02 VMware/

These may include:

VMware VM configuration
Running VM
System configuration
Sysbench result
Comparison

Comparison screenshots will be stored in:

Screenshots/Comparison/
14. Repository Structure
Cloud-Computing-Lab/
│
├── README.md
│
└── CC-Experiment-01-Hypervisor-Analysis/
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
15. Conclusion

This experiment provides practical experience with virtualization and
hypervisor technologies.

Proxmox VE is evaluated as a Type-1 hypervisor and VMware Workstation is
evaluated as a Type-2 hypervisor.

Both environments use comparable Ubuntu virtual machines and the same
Sysbench CPU benchmark.

The final conclusion will be based on the actual benchmark measurements,
performance comparison, resource observations, and graphical analysis
obtained during the experiment.

16. References
Cloud Computing Laboratory Manual – Performance Analysis of Type-1
and Type-2 Hypervisors.
Proxmox VE documentation.
VMware Workstation documentation.
Sysbench documentation.
