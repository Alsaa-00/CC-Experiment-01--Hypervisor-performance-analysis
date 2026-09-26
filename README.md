# Cloud Computing Lab

## Experiment 01
Performance Analysis of Type-1 and Type-2 Hypervisors

## Objective
To configure, monitor, and compare the performance of a Type-1 Hypervisor (Proxmox VE) and a Type-2 Hypervisor (VMware Workstation) by running a CPU benchmark on identically provisioned Virtual Machines.

## Tools Used
*   **Type-1 Hypervisor:** Proxmox VE
*   **Type-2 Hypervisor:** VMware Workstation
*   **Guest Operating System:** Ubuntu
*   **Benchmarking Tool:** Sysbench

## Experiment Overview
This experiment involves setting up Ubuntu VMs with identical hardware specifications (2 vCPU, 2 GB RAM, 20 GB Disk) on both Proxmox VE and VMware Workstation. A CPU benchmark using `sysbench` is executed to measure and compare the computational performance of both hypervisor architectures.

## Repository Structure
```
Cloud-Computing-Lab/
│
├── README.md
│
└── CC-Experiment-01-Hypervisor-Analysis/
    │
    ├── README.md
    ├── LAB_REPORT.md
    │
    ├── results/
    │   └── performance-analysis.md
    │
    ├── screenshots/
    │   ├── Part-A/
    │   │   └── output/
    │   └── Part-B/
    │       └── output/
    │
    └── scripts/
```

## Author
**Alsaba Awati**  
*Computer Science & Artificial Intelligence (CSE-AI), 5th Semester*  
*Roll No / USN:* **01fe25bci705**
