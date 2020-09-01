# s6-overlay-stage
[s6-overlay](https://github.com/just-containers/s6-overlay) is a series of init scripts and utilities to ease creating Docker images using [s6](http://skarnet.org/software/s6/overview.html) as a process supervisor.  

The images in this repository contain _only_ the unpacked s6-overlay.  This repo is not intended to be used directly, but rather consumed in other `Dockerfile`s as a multi-platform and reusable build stage.  Example usage:
```
FROM ...
COPY --from=arpaulnet/s6-overlay-stage:2.0 / /
RUN ...
```

## Architectures
This repository uses multi-platform images via Docker manifests.  You do not need to use a platform-specific tag (although you can); Docker will automatically choose the appropriate architecture.  Currently, the supported architectures are:
* `x86`/`386`
* `x86_64`/`amd64`
* `arm`/`arm32v6`
* `armhf`/`arm32v7`
* `arm64`/`arm64v8`
* `ppc64le`

## Tags
In addition to `latest`, this repository uses semantic versioned tags:
* major version (ex `2`)
* minor version (ex: `2.0`)
* patch version (ex: `2.0.0`)
* release version (ex: `2.0.0.1`)

These tags will be updated monthly from the latest release of s6-overlay.
