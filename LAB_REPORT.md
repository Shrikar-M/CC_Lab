# Cloud Computing Laboratory Report

## Performance Observation of Type-1 and Type-2 Hypervisors

**Experiment:** Ubuntu VM Provisioning and CPU Benchmarking  
**Platforms:** Proxmox VE (KVM) and VMware Workstation  
**Benchmark:** `sysbench cpu --cpu-max-prime=20000 run`

---

## 1. Objective

To configure an Ubuntu virtual machine on a Type-1 hypervisor and a Type-2 hypervisor, verify the guest system, monitor system resources, and compare CPU benchmark performance using throughput and latency measurements.

---

## 2. Background

A **Type-1 hypervisor** runs directly on the physical hardware and provides virtualization services to virtual machines. Proxmox VE uses KVM-based virtualization with the Linux kernel to host virtual machines.

A **Type-2 hypervisor** runs as software on top of a host operating system. VMware Workstation is an example of a Type-2 hypervisor.

Both types of hypervisors can run guest operating systems, but they differ in their architecture, management model, host environment, and resource handling.

---

## 3. Configuration

| Setting | Proxmox VE | VMware Workstation |
|---|---|---|
| Hypervisor Type | Type-1 | Type-2 |
| Guest OS | Ubuntu | Ubuntu |
| Virtual CPUs | 2 vCPU | 2 vCPU |
| Memory | 2 GB | 2 GB |
| Virtual Disk | 20 GB | 20 GB |

---

## 4. Procedure

### Part A — Proxmox VE

1. Created a virtual machine in Proxmox VE with 2 virtual CPUs, 2 GB memory, and a 20 GB virtual disk.
2. Installed and started the Ubuntu guest operating system.
3. Opened the Ubuntu console and verified the guest system configuration.
4. Checked CPU, memory, disk, and system information.
5. Monitored the system resources during execution.
6. Installed Sysbench in the Ubuntu guest.
7. Ran the CPU benchmark using a prime limit of 20,000.
8. Recorded the benchmark output for performance comparison.

### Type-1 Hypervisor — Proxmox VE

| Parameter | Value |
|---|---|
| Hypervisor | Proxmox VE |
| Hypervisor Type | Type-1 |
| Guest OS | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB |
| Disk | 20 GB |
| Total Execution Time | 10.0005 s |
| Total Events | 17,494 |
| Events per Second | 1,749.16 |
| Average Latency | 0.57 ms |

---

### Part B — VMware Workstation

1. Created an Ubuntu virtual machine using VMware Workstation.
2. Configured the virtual machine with 2 virtual CPUs, 2 GB memory, and a 20 GB virtual disk.
3. Started the Ubuntu guest operating system.
4. Verified the hostname, CPU, memory, disk, and system information.
5. Monitored the guest system resources during execution.
6. Installed Sysbench in the Ubuntu guest.
7. Ran the same CPU benchmark with a prime limit of 20,000.
8. Recorded the benchmark output for comparison with the Proxmox VE results.

### Type-2 Hypervisor — VMware Workstation

| Parameter | Value |
|---|---|
| Hypervisor | VMware Workstation |
| Hypervisor Type | Type-2 |
| Guest OS | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB |
| Disk | 20 GB |
| Total Execution Time | 10.0006 s |
| Total Events | 7,077 |
| Events per Second | 707.43 |
| Average Latency | 1.41 ms |

---

## 5. CPU Benchmark

The following Sysbench command was used for both virtual machines:

`sysbench cpu --cpu-max-prime=20000 run`

The benchmark performs CPU-intensive calculations by finding prime numbers up to 20,000.

The main performance metrics obtained from the benchmark are:

- **Total Execution Time** — Total time taken by the benchmark.
- **Total Events** — Number of calculations completed.
- **Events per Second** — Number of calculations completed per second. Higher is better.
- **Average Latency** — Average time taken to complete an event. Lower is better.

---

## 6. Results

### 6.1 Proxmox VE Results

| Metric | Value |
|---|---:|
| Total Execution Time | 10.0005 s |
| Total Events | 17,494 |
| Events per Second | 1,749.16 |
| Average Latency | 0.57 ms |

### 6.2 VMware Workstation Results

| Metric | Value |
|---|---:|
| Total Execution Time | 10.0006 s |
| Total Events | 7,077 |
| Events per Second | 707.43 |
| Average Latency | 1.41 ms |

---

## 7. Side-by-Side Comparison

| Parameter | Type-1 — Proxmox VE | Type-2 — VMware Workstation |
|---|---:|---:|
| Total Execution Time | 10.0005 s | 10.0006 s |
| Total Events | 17,494 | 7,077 |
| Events per Second | 1,749.16 | 707.43 |
| Average Latency | 0.57 ms | 1.41 ms |

### Throughput Comparison

The relative throughput difference can be calculated as:

`(1749.16 - 707.43) / 707.43 × 100 ≈ 147.24%`

Therefore, Proxmox VE achieved approximately **147.24% higher measured throughput** than VMware Workstation in these test runs.

Another way to express the result is:

`1749.16 / 707.43 ≈ 2.47`

Thus, Proxmox VE achieved approximately **2.47× the measured CPU throughput** of VMware Workstation.

---

## 8. Interpretation of Results

### Total Execution Time

The execution times of both virtual machines were almost identical.

- Proxmox VE: **10.0005 seconds**
- VMware Workstation: **10.0006 seconds**

Therefore, there is very little difference in total execution time for these particular runs.

### Total Events

Proxmox VE completed **17,494 events**, while VMware Workstation completed **7,077 events**.

This indicates that the Proxmox VE configuration completed significantly more CPU calculations during the benchmark.

### Events per Second

Proxmox VE achieved:

**1,749.16 events/sec**

VMware Workstation achieved:

**707.43 events/sec**

Since a higher events-per-second value indicates higher benchmark throughput, Proxmox VE performed better in this test.

### Average Latency

Proxmox VE recorded an average latency of **0.57 ms**, while VMware Workstation recorded **1.41 ms**.

The lower latency observed on Proxmox VE indicates better measured responsiveness during this CPU benchmark.

---

## 9. Commands Used

The following commands were used during the experiment to verify the Ubuntu guest system and perform the CPU benchmark:

### System Information

`hostnamectl`

`lscpu`

`free -h`

`df -h`

`top`

### Package Installation

`sudo apt update`

`sudo apt install -y sysbench`

### Sysbench Version

`sysbench --version`

### CPU Benchmark

`sysbench cpu --cpu-max-prime=20000 run`

---

## 10. Conclusion

The experiment demonstrated the provisioning and execution of Ubuntu virtual machines on both a **Type-1 hypervisor (Proxmox VE)** and a **Type-2 hypervisor (VMware Workstation)**.

Under the tested configuration, Proxmox VE achieved **1,749.16 events/sec**, while VMware Workstation achieved **707.43 events/sec**.

Proxmox VE therefore achieved approximately **2.47× the measured CPU throughput** of VMware Workstation. It also recorded a lower average latency of **0.57 ms**, compared with **1.41 ms** for VMware Workstation.

The results show better measured CPU benchmark performance for the Proxmox VE configuration in this experiment. However, the result does not mean that Type-1 hypervisors will always be faster than Type-2 hypervisors, because performance can also depend on hardware, VM configuration, CPU allocation, host operating system, virtualization settings, and system workload.

Therefore, based on the measured results, **Proxmox VE demonstrated better CPU benchmark performance than VMware Workstation for the tested configurations.**

---

## 11. Screenshot Index

### Type-1 Hypervisor — Proxmox VE

The screenshots related to Proxmox VE configuration, Ubuntu execution, system verification, resource monitoring, and Sysbench results are available in:

`screenshots/Type1-proxmox/`

### Type-2 Hypervisor — VMware Workstation

The screenshots related to VMware Workstation configuration, Ubuntu execution, system verification, resource monitoring, and Sysbench results are available in:

`screenshots/Type2-vmware/`

### Comparison Screenshots

Screenshots used for comparing the Type-1 and Type-2 hypervisor results are available in:

`screenshots/comparison/`
