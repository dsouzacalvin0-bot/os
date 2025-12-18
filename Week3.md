# week 3 Application Selection for Performance Testing

# Introduction

Phase 3 focuses on selecting a range of applications that can be used to evaluate system performance under different types of workload. The purpose of this phase is to ensure that the server is tested in a realistic and structured way, covering multiple aspects of operating system behaviour rather than relying on a single test.

This section introduces the chosen applications, each representing a different workload type such as CPU-intensive, memory-intensive, disk I/O-intensive, network-intensive, and server-based workloads. An application selection matrix is used to justify why each tool or service was chosen and what part of the system it is expected to stress.

The phase also documents the installation process for each application using SSH and command-line tools only. In addition, expected resource usage is outlined to provide a reference point for later performance testing, along with a monitoring strategy that explains how CPU, memory, disk, and network activity will be measured for each application during testing.

# Application Selection Overview

This section explains the purpose of selecting multiple applications for performance testing. Each application represents a different workload type so that various aspects of system behaviour can be tested rather than focusing on a single resource.

# Application Selection Matrix

The application selection matrix lists all chosen applications along with their workload type and justification. This makes it clear why each application was selected and how it contributes to evaluating CPU usage, memory consumption, disk activity, or network performance.

# Installation Process

This section documents how each application was installed on the server using SSH and command-line tools only. Exact installation commands are included to demonstrate correct package management and ensure the installation steps are clear and repeatable.

# Commands


``` bash
#adds the user named celvin_bot in users by default
sudo adduser celvin_bot

#assigning them sudo privilege

sudo usermod -aG sudo celvin_bot
#above command will add the user to the sudoers group.


## we can use ssh for verification .

```

# Expected Resource Usage and Monitoring Strategy

Expected resource usage is outlined for each application to provide an idea of how the system is likely to behave during testing. A monitoring strategy is also described to explain which tools will be used to measure CPU, memory, disk, and network performance for each workload.

## 3. Expected Resource Profiles

- **stress-ng (CPU Test)**
  - **Expected:**  
    CPU usage is expected to increase to near 100% on the core being tested. Memory usage and disk I/O should remain low.

- **stress-ng (Memory Test)**
  - **Expected:**  
    Memory usage shown by `free -h` will increase as available memory decreases. Swap usage may occur, while CPU usage remains moderate.

- **dd (Disk Test)**
  - **Expected:**  
    Disk I/O metrics from `iostat` will show high write throughput. CPU wait time is expected to increase due to disk access.

- **iperf3 (Network Test)**
  - **Expected:**  
    Network traffic will approach the maximum bandwidth of the virtual network adapter. CPU usage will remain moderate while processing network traffic.

---

## 4. Monitoring Strategy and Test Commands

- **stress-ng (CPU)**
  - **Test Command (Server):**
    ```bash
    stress-ng --cpu 1 --timeout 60s
    ```
  - **Monitoring (via SSH):**
    ```bash
    uptime
    top -b -n 1 | grep "Cpu(s)"
    ```

- **stress-ng (Memory)**
  - **Test Command (Server):**
    ```bash
    stress-ng --vm 1 --vm-bytes <SRV_RAM>G --timeout 60s
    ```
  - **Monitoring (via SSH):**
    ```bash
    free -h
    ```

- **dd (Disk I/O)**
  - **Test Command (Server):**
    ```bash
    dd if=/dev/zero of=testfile bs=1G count=1 oflag=direct
    ```
  - **Monitoring (via SSH):**
    ```bash
    iostat -xz 1 10
    ```

- **iperf3 (Network)**
  - **Test Command (Server):**
    ```bash
    iperf3 -s
    ```
  - **Test Command (Workstation):**
    ```bash
    iperf3 -c <server_IP_address>
    ```
