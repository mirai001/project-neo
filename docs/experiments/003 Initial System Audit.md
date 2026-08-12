# Experiment 003 — Initial System Audit

## Objective

Establish the initial state of the NEO compute node before making
system-level configuration changes.

The purpose of this audit is to understand the system rather than
immediately modify or harden it.

---

## Environment

| Component | Result |
|---|---|
| Cloud Provider | Oracle Cloud |
| Region | Indonesia North (Batam) |
| Operating System | Ubuntu 24.04.4 LTS |
| Architecture | x86_64 |
| Kernel | Linux 6.17.0-1019-oracle |
| Logical CPUs | 4 |
| Memory | ~15 GiB |
| Swap | 0 B |
| Root Filesystem | ~193 GB |
| Network Interface | `enp0s5` |
| Private IP | `<PRIVATE_IP>` |
| MTU | 9000 |

---

## System State

### Uptime

The instance had been running for approximately 5 days and
20 hours at the time of inspection.

# The system load was:
SSH configuration:
  sudo sshd -T | grep -E \
  '^(port|permitrootlogin|passwordauthentication|pubkeyauthentication|kbdinteractiveauthentication)'

observed configuration:
  port 22
  permitrootlogin without-password
  pubkeyauthentication yes
  passwordauthentication no
  kbdinteractiveauthentication no

SSH public-key authentication is enabled while password
authentication and keyboard-interactive authentication are disabled.
This provides a reasonable initial authentication baseline.
The SSH port remains at the default port 22.
No change to the SSH configuration was made during this audit.

Firewall configuration:
public
dhcpv6-client
ssh

open application ports:
25565/tcp
25565/udp
24454/tcp
24454/udp

no rich rules

These ports are intentionally exposed for Minecraft-related
services used by the NEO node.

At the time of the audit, no process was listening on these ports
because the Minecraft service had not yet been started.

Therefore, the firewall configuration is intentional and should
not be considered an unused firewall rule.

Active System Services

# Several system and cloud-provider services were observed running,
including:

OpenSSH
firewalld
rpcbind
systemd-networkd
systemd-resolved
systemd-timesyncd
systemd-journald
cron
unattended-upgrades
Oracle Cloud Agent
Oracle Unified Monitoring Agent
snapd
udisks2

These services were not removed during the initial audit.



