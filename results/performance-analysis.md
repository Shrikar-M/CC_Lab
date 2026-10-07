# Performance Analysis Results

## 1. Objective

The objective of this experiment is to compare the CPU performance of a **Type-1 hypervisor (Proxmox VE)** and a **Type-2 hypervisor (VMware Workstation)** using the Sysbench CPU benchmark.

Both virtual machines were configured with similar resources to ensure a fair comparison.

---

## 2. Benchmark Used

The following Sysbench command was used:

`sysbench cpu --cpu-max-prime=20000 run`

### What the Command Does

- It calculates prime numbers up to **20,000**.
- The benchmark places a significant load on the CPU.
- It measures the number of calculations completed during the test.
- **Higher events per second indicate better CPU performance.**
- **Lower average latency indicates better performance.**

---

## 3. Type-1 Hypervisor — Proxmox VE

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

## 4. Type-2 Hypervisor — VMware Workstation

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

## 5. Side-by-Side Comparison

| Parameter | Type-1 — Proxmox VE | Type-2 — VMware Workstation |
|---|---:|---:|
| Total Execution Time | 10.0005 s | 10.0006 s |
| Total Events | 17,494 | 7,077 |
| Events per Second | 1,749.16 | 707.43 |
| Average Latency | 0.57 ms | 1.41 ms |

---

## 6. Interpretation of Results

### Total Execution Time

The total execution time represents the amount of time taken by the benchmark to complete its test.

- Proxmox VE: **10.0005 s**
- VMware Workstation: **10.0006 s**

The execution times are almost identical, so execution time alone does not show a significant performance difference.

### Total Events

Total events represent the number of CPU calculations completed during the benchmark.

- Proxmox VE: **17,494 events**
- VMware Workstation: **7,077 events**

Proxmox VE completed significantly more events during the benchmark.

### Events per Second

Events per second is the main performance indicator in this benchmark.

- Proxmox VE: **1,749.16 events/sec**
- VMware Workstation: **707.43 events/sec**

Proxmox VE achieved approximately **2.47× higher throughput** than VMware Workstation.

### Average Latency

Average latency represents the average time required to complete an individual calculation.

- Proxmox VE: **0.57 ms**
- VMware Workstation: **1.41 ms**

The lower latency of Proxmox VE indicates better CPU responsiveness during the benchmark.

---

## 7. Performance Comparison

Based on the benchmark results, Proxmox VE performed better than VMware Workstation.

| Metric | Better Hypervisor | Reason |
|---|---|---|
| Execution Time | Proxmox VE | Slightly lower |
| Total Events | Proxmox VE | More calculations completed |
| Events per Second | Proxmox VE | Higher throughput |
| Average Latency | Proxmox VE | Lower latency |

---

## 8. Conclusion

The Sysbench CPU benchmark shows that **Proxmox VE (Type-1)** provided better CPU performance than **VMware Workstation (Type-2)** under the tested configuration.

Proxmox VE achieved **1,749.16 events/sec**, while VMware Workstation achieved **707.43 events/sec**. This means that Proxmox VE achieved approximately **2.47 times the CPU throughput** of VMware Workstation in this benchmark.

Proxmox VE also recorded a lower average latency of **0.57 ms**, compared with **1.41 ms** for VMware Workstation.

The difference can be attributed to the virtualization architecture. A Type-1 hypervisor runs directly on the physical hardware, whereas a Type-2 hypervisor runs on top of a host operating system, which can introduce additional overhead.

Therefore, based on this CPU benchmark, **Proxmox VE demonstrated significantly better CPU performance than VMware Workstation**.

> **Final Conclusion:** For CPU-intensive workloads, a Type-1 hypervisor such as Proxmox VE can provide better performance than a Type-2 hypervisor such as VMware Workstation under comparable virtual machine configurations.
