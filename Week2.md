# week 2  Security Planning and Testing Methodology

# Introduction

Phase 2 focuses on planning how the system will be secured and how its performance will be tested later in the project. Before making any changes to the server, it is important to define a clear security baseline and a consistent testing approach so that results can be measured accurately.

This section explains the planned performance testing methodology, including how the server will be monitored remotely from the workstation to reduce any impact on system performance. It also outlines a security configuration checklist covering key areas such as SSH hardening, firewall configuration, access control, automatic updates, user permissions, and basic network security.

In addition, a threat model is used to identify realistic security risks that could affect the system. For each threat, suitable mitigation strategies are proposed to guide the security decisions made in later phases. This planning stage helps ensure that security and performance are considered together throughout the rest of the coursework.

# Application Selection Overview

This section explains the purpose of selecting multiple applications for performance testing. Each application represents a different workload type so that various aspects of system behaviour can be tested rather than focusing on a single resource.

# Application Selection Matrix

The application selection matrix lists all chosen applications along with their workload type and justification. This makes it clear why each application was selected and how it contributes to evaluating CPU usage, memory consumption, disk activity, or network performance.

# Installation Process

This section documents how each application was installed on the server using SSH and command-line tools only. Exact installation commands are included to demonstrate correct package management and ensure the installation steps are clear and repeatable.

# Expected Resource Usage and Monitoring Strategy

Expected resource usage is outlined for each application to provide an idea of how the system is likely to behave during testing. A monitoring strategy is also described to explain which tools will be used to measure CPU, memory, disk, and network performance for each workload.
