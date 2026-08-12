# 004 — Minecraft Server Deployment

## Objective

Deploy the first real workload on the NEO compute node and verify that an existing Minecraft world can be migrated and operated successfully on the server.

## Environment

- Cloud Provider: Oracle Cloud
- Operating System: Ubuntu 24.04 LTS
- Workload: Minecraft Paper Server
- Paper Version: 26.2
- World: `hostel_world`

## Deployment

The Minecraft server was installed and configured on the NEO compute node as the first application workload.

The server uses Paper as the Minecraft server implementation.

## World Migration

An existing Minecraft world was migrated to the NEO server.

The migrated world is:

```text
hostel_world
```

After the migration, the Paper server successfully loaded the world and the world is currently running on the NEO node.

## Initial Result

Deployment successful.

The first NEO workload is operational:

```text
Oracle Cloud VPS
└── Ubuntu
    └── Paper Minecraft Server
        └── hostel_world
```

This confirms that the NEO compute node is capable of hosting a persistent application workload and its associated world data.

## Verification

The following conditions were confirmed after deployment:

- Minecraft Paper server is running.
- `hostel_world` was successfully migrated.
- `hostel_world` was successfully loaded by the Paper server.
- The world is currently operational.

## Significance

This experiment marks the transition from infrastructure provisioning to running an actual workload on NEO.

The Minecraft server is intentionally being used as the first workload because it provides a practical environment for developing operational skills such as Linux administration, process management, networking, data management, backup, monitoring, and recovery.

The current deployment is functional, but it should not yet be considered a fully automated or highly resilient service. Future experiments will focus on making the workload easier to operate, recover, and reproduce.

## Next Steps

Potential follow-up work includes:

1. Service/process management
2. Automated server startup and shutdown
3. Backup and restore procedures
4. Resource and service monitoring
5. Log management
6. Network and firewall review
7. Recovery and rebuild procedures
8. Configuration documentation
