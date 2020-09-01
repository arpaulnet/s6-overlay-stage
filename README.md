# s6-overlay-stage
[s6-overlay](https://github.com/just-containers/s6-overlay) is a series of init scripts and utilities to ease creating Docker images using [s6](http://skarnet.org/software/s6/overview.html) as a process supervisor.  The images within this repository contain a root filesystem with _only_ s6-overlay within.  This repository is not intended to be used directly, but rather consumed in other Dockerfiles.  It is intended to be a multi-platform, reusable, build stage.  Example usage:
```
FROM ...
COPY --from=arpaulnet/s6-overlay-stage:2.0.0.1 / /
RUN ...
```

## Architectures
This repository uses multi-platform images via Docker manifests.  You do not need to use a platform-specific tag (although you can); Docker will automatically choose the appropriate architecture.  Currently, the supported architectures are:
* `x86`/`386`
* `x86_64`/`amd64`
* `arm`/`armv6`
* `armhf`/`armv7`
* `arm64`
* `ppc64le`

## Tags
In addition to `latest`, this repository uses semantic versioned tags:
* release version (ex: `2.0.0.1`)
* patch version (ex: `2.0.0`)
* minor version( (ex: `2.0`)
* major version (ex `2`)
