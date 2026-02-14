# Home Project

This repository contains Docker Compose configurations for deploying a set of self-hosted services locally or on a home server, with Tailscale used to securely access those services over the internet.

Key points
- Deploys multiple service stacks as Docker containers (each service has its own `compose.yaml` and JSON metadata).
- Uses Tailscale to provide secure, private network access from anywhere on your tailnet.

Services included (each folder contains a `compose.yaml` and a service JSON):
- `checkmk`
- `Firefly_III`
- `Immich`
- `jellyfin`
- `Jellyseerr`
- `Mealie`
- `n8n`
- `nextcloud`

Prerequisites
- Docker Engine / Docker Desktop (with Docker Compose support)
- A Tailscale account and Tailscale installed on the host (or configured in a container)

Quick start
1. Install and login to Tailscale on the host: follow Tailscale docs to join your tailnet.
2. For each service folder, start the stack:

```bash
cd <service-folder>
docker compose -f compose.yaml up -d
```

3. Access services via their local ports or via the host's Tailscale IP (recommended for remote access).

Notes
- The JSON files next to each `compose.yaml` contain service-specific metadata and environment examples.
- If you prefer running Tailscale in a container, ensure the container can advertise/route the necessary services or use the host network.

Where to go next
- Customize `compose.yaml` files per service to change ports, volumes, or environment variables.
- Consider adding a management script or top-level `docker compose` aggregator if you want to bring up multiple services at once.

Maintainer
- See repository owner for contact and further instructions.

Enjoy your self-hosted stack — securely accessible via Tailscale!