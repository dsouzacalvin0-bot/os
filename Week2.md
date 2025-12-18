# week 2  Security Planning and Testing Methodology

# Introduction

Phase 2 focuses on planning how the system will be secured and how its performance will be tested later in the project. Before making any changes to the server, it is important to define a clear security baseline and a consistent testing approach so that results can be measured accurately.

This section explains the planned performance testing methodology, including how the server will be monitored remotely from the workstation to reduce any impact on system performance. It also outlines a security configuration checklist covering key areas such as SSH hardening, firewall configuration, access control, automatic updates, user permissions, and basic network security.

In addition, a threat model is used to identify realistic security risks that could affect the system. For each threat, suitable mitigation strategies are proposed to guide the security decisions made in later phases. This planning stage helps ensure that security and performance are considered together throughout the rest of the coursework.

# Application Selection Overview

This section explains the purpose of selecting different applications for performance testing. Each application is chosen to represent a specific type of workload so that different aspects of system behaviour can be analysed.

# Application Selection Matrix

An application selection matrix is used to list each chosen application, its workload type, and the reason it was selected. This helps justify how each application contributes to testing CPU, memory, disk, or network performance.

# Installation Process

This section documents how each application was installed on the server using SSH and command-line tools. Exact installation commands are included to show how the setup was completed and to ensure the process can be repeated.

# Expected Resource Usage and Monitoring Strategy

Expected resource usage is outlined for each application to predict how it will affect system performance. A monitoring strategy is also described to explain how CPU, memory, disk, and network activity will be measured during testing.
