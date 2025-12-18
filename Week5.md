# week 5  Advanced Security and Monitoring Infrastructure 

# Introduction

Phase 5 focuses on improving the security of the server and setting up basic monitoring to observe how the system behaves over time. This phase builds on the security controls introduced earlier and aims to make the system more resistant to common attacks while allowing its performance to be monitored remotely.

In this section, access control is implemented using SELinux or AppArmor, and automatic security updates are configured to keep the system up to date. Fail2ban is also set up to help detect and block repeated unauthorised login attempts. Alongside these controls, two scripts are created: one to verify that all security settings are correctly applied on the server, and another to monitor system performance remotely from the workstation using SSH.

All scripts are fully commented and demonstrated to show how they work and why they are used. This phase helps ensure the system is both secure and observable before moving on to detailed performance testing.

# Installation document 
``` bash

##installation documentation.

sudo apt update && sudo apt install unattended-upgrades -y

## configuration

sudo dpkg-reconfigure -plow unattended-upgrades


## verification can be done using.

cat /etc/apt/apt.conf.d/50unattended-upgrades | grep "security"

```
# Intrution Detection 
``` bash

#intrustion detection

sudo apt install fail2ban -y

# we create a copy so that we dont damage the main configuration file.
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local



```
