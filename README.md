# Meme Search for Unraid

> [!WARNING]
> This repository is an **experimental community integration**. It does not yet
> contain an installable image or Community Applications template and is not an
> officially supported Meme Search deployment.

This project will explore an all-in-one image and Unraid Community Applications
template built from versioned upstream Meme Search release images. Keeping the
platform packaging separate gives it an independent release, security, backup,
upgrade, and support lifecycle without forking the core application.

## Current security boundary

Meme Search currently supports loopback-only operation. Its web and settings
interface does not provide end-user authentication. A normal Unraid mapped port
is reachable from the Unraid server or LAN, so an initial package must not claim
that publishing only the web port preserves the core project's supported
loopback boundary.

PostgreSQL and the Python image-description service must remain private. Do not
publish this integration to Community Applications until its threat model,
network defaults, secret handling, upgrade behavior, and backup/restore behavior
have been reviewed.

## Proposed first milestone

1. Document the Unraid networking and storage contract.
2. Pin versioned upstream images to immutable digests or verified provenance.
3. Supervise PostgreSQL, migrations, the Rails app and worker, and the Python
   generator without exposing internal services.
4. Define separate persistent app state, meme library, and disposable model
   cache paths.
5. Add automated clean-install, upgrade, backup, and restore tests.
6. Publish a beta only after the security and data-lifecycle review passes.

The originating proposal is
[Meme Search Discussion #220](https://github.com/neonwatty/meme-search/discussions/220).

## Upstream

- [Meme Search core](https://github.com/neonwatty/meme-search)
- [Core security policy](https://github.com/neonwatty/meme-search/security/policy)
- [Supported Docker Compose deployment](https://github.com/neonwatty/meme-search/blob/main/docker-compose.yml)
