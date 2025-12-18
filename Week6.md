# week 6 Performance Evaluation and Analysis

# Introduction

Phase 6 focuses on testing the performance of the server and observing how the operating system behaves under different workloads. The aim is to measure how system resources are used and to identify any performance limitations.

In this phase, each selected application is tested using baseline and load testing scenarios. Metrics such as CPU usage, memory usage, disk activity, network performance, and response times are monitored and compared. The results are recorded in tables and shown using charts and graphs to make the data easier to understand.

Based on the findings, performance bottlenecks are identified and optimisation changes are applied. The system is then tested again to measure any improvements. This phase provides clear evidence of how configuration changes affect overall system performance.

# Testing Tools

Stress-ng is a system stress-testing tool used to load CPU, memory, disk, and other resources to evaluate system stability under pressure.
iperf3 measures network performance by testing bandwidth, latency, and throughput between two hosts.
dd is a low-level Unix utility used for raw data copying, often for disk benchmarking, backups, and data wiping.

## 1. CPU stress
``` bash
sudo apt update
sudo apt install stress-ng

# stress command :

stress-ng --cpu 2 --timeout 120s

```

# Network through put test
