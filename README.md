# Kora

## Introduction

This repository provides a small Docker Compose setup for running [Kora](https://getkora.org) locally.

## Initial setup

### Requirements

- [Git](https://git-scm.com/downloads)
- [Docker](https://docs.docker.com/get-started/get-docker/)

Windows and macOS users should install Docker Desktop. On Windows, run the commands from Git Bash or WSL.

### Installation

Open Git Bash (Windows), or from the terminal (Mac / Linux), paste:

```bash
git clone --depth 1 https://github.com/kofm/kora-app kora
cd kora
./ko
```

Select **Start Kora** from the menu. On first start, it generates the required configuration file, starts the services, and offers to create an administrator user.

After startup, open http://localhost:8000 in a browser and log in with the user you created. The included application binds to `localhost` only, so Kora will not be reachable from other machines without tweaking the configuration.

## `ko` commands

Run `./ko` with no arguments to open the interactive menu:

```text
0. Start Kora
1. Stop Kora
2. Update Kora
3. Backup data
4. Restore backup
5. Create admin user
q. Quit
```

The same operations are available as direct commands:

```bash
./ko start             # start Kora
./ko stop              # stop Kora
./ko backup            # create a backup in the current directory
./ko restore           # restore one of the available backups
./ko update            # update Kora
./ko createsuperuser   # create an administrator user
```

## Backups and restore

Create a backup with:

```bash
./ko backup
```

Backups are written to the repository directory with names like:

```text
kora_db_bk_YYYY-MM-DD-HHMMSS.backup
```

Restore a backup with:

```bash
./ko restore
```

This command lists available backups and asks which one to restore.

## Updates

Update to the latest kora version with:

```bash
./ko update
```

The update command create a backup, updates kora, and then restarts it.

## Documentation

Check out documentation at https://docs.getkora.org

## License

Copyright (C) 2026 Gabriele Mongiano.

Kora is free software licensed under the GNU Affero General Public License version 3 or later (AGPL-3.0-or-later). See [LICENSE](LICENSE) for details.
