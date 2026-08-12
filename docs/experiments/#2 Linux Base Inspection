# Experiment 002 — Linux Baseline Inspection

## Objective

Inspect the initial state of the NEO compute node before making
system-level configuration changes.

## Environment

- Hostname: `trial-vnic`
- User: `ubuntu`
- Operating System: Ubuntu 24.04.4 LTS
- Kernel: Linux 6.17.0-1019-oracle
- Architecture: x86_64
- Logical CPUs: 4
- Memory: ~15 GiB
- Swap: 0 B
- Root filesystem: ~193 GB
- Network interface: `enp0s5`
- Private IP: `10.0.0.214/24`
- MTU: 9000

## System State

- Uptime: approximately 5 days 20 hours
- Load average: 0.00, 0.00, 0.00
- Logged-in users: 2
- Root filesystem usage: approximately 3%

## Active Services

Important active services observed:

- `ssh.service`
- `firewalld.service`
- `systemd-networkd.service`
- `systemd-resolved.service`
- `systemd-timesyncd.service`
- `systemd-journald.service`
- `cron.service`
- `unattended-upgrades.service`
- Oracle Cloud Agent
- Snap Daemon
- Unified Monitoring Agent

## Observations

The provisioned VM already includes several system and
cloud-provider services.

The firewall is active and unattended upgrades are enabled.

The VM currently has very low system load and substantial
available CPU, memory, and storage capacity.

## Findings

The cloud provider's reported resource configuration and the
resources exposed to the guest OS should be distinguished.

The instance was configured with 2 OCPUs in Oracle Cloud,
while the guest OS reports 4 logical CPUs.

## Next Step

Proceed with NEO system configuration and security hardening.
