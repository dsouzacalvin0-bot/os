# week 1 System Planning and Distribution Selection  
  ![](week1_os/sys.png)

  # Introduction

Phase 1 focuses on planning a virtual operating system deployment and justifying the technical decisions made at this early stage of the project. The aim is to design a simple but effective dual-system architecture that supports secure remote administration and provides a foundation for later security and performance testing.

This phase outlines the overall system architecture, including a headless Linux server and a separate workstation used to access the server via SSH. It also explains the reasoning behind the chosen server distribution and workstation setup, along with the virtual network configuration used to allow controlled communication between the two systems.

Finally, basic system information is gathered using standard command-line tools to confirm the initial configuration of both systems. This establishes a clear baseline that will be referenced in later phases as the system is secured, monitored, and tested under different workloads.

# Operating sytems 
Ubuntu Server 22.04
Ubuntu Desktop 22.04

Ubuntu Server 22.04 and Ubuntu 22.04 Desktop were chosen because they provide a stable, well-supported, and practical environment for this project while closely reflecting real-world industry use. Ubuntu Server 22.04 is a Long Term Support (LTS) release, which means it receives security updates and maintenance for several years, making it a reliable choice for a secure headless server. It also includes built-in security features such as AppArmor, strong package management, and excellent compatibility with tools like UFW, fail2ban, and Lynis, all of which are required for this coursework. Ubuntu 22.04 Desktop is an ideal workstation choice because it uses the same base system as the server, reducing compatibility issues and making administration more consistent and easier to understand. Its graphical interface simplifies development, monitoring, and documentation tasks while still allowing full command-line access via SSH. Together, these two systems offer a balanced setup that is stable, secure, widely documented, and well suited to learning Linux server administration and security best practices
