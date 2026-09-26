# Assetto Corsa EVO — Pterodactyl Egg

A ready-to-import Pterodactyl egg for the **Assetto Corsa EVO dedicated server**.

This project is based on a Pterodactyl-focused fork of [zino1337/acevo-server](https://github.com/zino1337/acevo-server), maintained at [0herculabs/acevo-server](https://github.com/0herculabs/acevo-server).

## Features

- Assetto Corsa EVO dedicated server
- Proton support
- SteamCMD install and update flow
- Web dashboard support
- Persistent server data under `/home/container`
- No custom Wings mounts required
- Configurable server name
- Configurable TCP, UDP, HTTP and dashboard ports
- Automatic synchronization of the egg from the source repository

## Installation

1. Download `egg-assetto-corsa-evo.json`.
2. Open the Pterodactyl admin panel.
3. Go to **Nests → Import Egg**.
4. Import the JSON file.
5. Create a server using the imported egg.
6. Add the required allocations and configure the Steam credentials.

## Default ports

| Purpose | Port | Protocol |
|---|---:|---|
| Game server | Primary allocation | TCP + UDP |
| HTTP / listing | 8080 by default | TCP |
| Web dashboard | 8090 by default | TCP |

The game TCP/UDP port is automatically taken from Pterodactyl's primary allocation. Make sure the HTTP/listing and dashboard ports also have matching allocations if you expose them externally.

## Main variables

- `STEAM_USERNAME`
- `STEAM_PASSWORD`
- `STEAM_AUTH_CODE`
- `SERVER_NAME`
- `SERVER_HTTP_PORT`
- `DASHBOARD_PORT`
- `DASHBOARD_USER`
- `DASHBOARD_PASSWORD`
- `AUTO_UPDATE`
- `STEAM_VALIDATE`
- `AUTO_START_SERVER`
- `ACEVO_FORCE_SOFTWARE_RENDERING`

## Docker image

```text
ghcr.io/0herculabs/acevo-server:pterodactyl
```

## Automatic synchronization

This repository automatically synchronizes the egg from:

```text
Repository: 0herculabs/acevo-server
Branch: pterodactyl
Path: pterodactyl/egg-assetto-corsa-evo.json
```

The workflow checks for changes every hour and can also be run manually from the **Actions** tab.

## Credits

- Original project: [zino1337/acevo-server](https://github.com/zino1337/acevo-server)
- Pterodactyl fork and egg: [0herculabs/acevo-server](https://github.com/0herculabs/acevo-server)
