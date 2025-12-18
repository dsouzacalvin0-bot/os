# week 7 Security Audit and System Evaluation

# Introduction 
Phase 7 focuses on reviewing the security of the system after all configuration and testing has been completed. The aim is to check how secure the server is and to see if there are any remaining issues that need attention.

In this phase, security scans are run using Lynis and network checks are carried out with nmap to see what is visible from the outside. SSH settings, access control, and running services are also reviewed to make sure they are set up correctly and that only necessary services are enabled.

The findings from these checks are documented in a security audit report, along with any improvements made and a discussion of remaining risks. This final phase helps to evaluate the overall security of the system and reflect on what has been learned during the project.


# Security scanning with Lynis:
Lynis was used to scan the system for security weaknesses and misconfigurations. It provides a security score and recommendations for improving the system.

This was the results before
  ![](week7_os/lynisbefore.png)

This is the results after 
  ![](week7_os/lynisafter.png)
  
# Network security assessment with nmap:
nmap was used to scan the server from the workstation to identify open ports and active network services. This allowed visibility of which services were exposed to the network and helped verify that only intended ports were accessible. The results were compared against the firewall configuration to confirm that firewall rules were correctly restricting unauthorised access.

# Access control verification:
Access control settings were reviewed to ensure that user permissions, SSH access restrictions, and security policies were correctly enforced. This included checking user accounts, sudo privileges, and authentication methods to confirm that administrative access was limited to authorised users only. These checks helped ensure that privilege escalation risks were minimised.

# Service audit:
All running services on the server were reviewed to identify which services were active and listening for connections. Each service was assessed to determine whether it was required for the system’s operation or testing activities. Unnecessary services were identified in order to reduce the system’s attack surface and improve overall security.

# System configuration review:
The overall system configuration was reviewed to ensure that security-related settings were applied consistently across the system. This included checking system services, network configuration, and security controls such as SSH and firewall settings. The review helped confirm that the system followed security best practices and aligned with the coursework requirements.


# Active Network Services and Listening Ports

This screenshot shows the output of the ss -tulpn command, which lists all active network connections and listening ports on the server. It displays which services are currently running, the ports they are listening on, and the processes associated with them, such as SSH, Apache, and iperf3. This helps identify which services are exposed on the network and supports the service audit by confirming that only required services are active.

  ![](week7_os/tulpnscore.png)
