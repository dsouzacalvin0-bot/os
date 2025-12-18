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

``` bash
stress-ng (CPU Test)
Expected: CPU usage will jump to 100% for each core being tested. Memory and disk I/O should remain low.
stress-ng (Memory Test)
Expected: Memory usage (free -h) will show "used" memory climb until "available" memory is very low. System will likely start using swap space. CPU usage may be moderate.
dd (Disk Test)
Expected: Disk I/O metrics (iostat) will show high megabytes written per second. The CPU will show a high waiting percentage for the disk.
iperf3 (Network Test)
Expected: Network traffic will max out the VM adapter's bandwidth. CPU usage will be moderate, as it processes network packets.
```
``` bash
stress-ng (CPU):
Test Command (Server): stress-ng --cpu 1 --timeout 60s
Monitoring (via SSH): uptime and top -b -n 1 | grep "Cpu(s)"
stress-ng (Memory):
Test Command (Server): stress-ng --vm 1 --vm-bytes <SRV_RAM>G --timeout 60s (Adjust SRV_RAM based on the choosen server platform).
Monitoring (via SSH): free -h before, during, and after the test.
dd (Disk I/O):
Test Command (Server): dd if=/dev/zero of=testfile bs=1G count=1 oflag=direct (This writes a 1GB file).
Monitoring (via SSH): iostat -xz 1 10 while the test runs to capture disk wMB/s.
iperf3 (Network):
Test Command (Server): iperf3 -s
Test Command (Workstation): iperf3 -c <server_IP_address> or GUI application.
Monitoring: The iperf3 client output itself provides the main metric (e.g., "Mbits/sec").
```
