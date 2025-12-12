# Docker Alpine Reproduction Case

## Dockerfile Description

This repository contains a minimal Dockerfile that demonstrates an issue with Alpine Linux package manager (`apk`) when running in certain Docker environments.

### Dockerfile Contents

```dockerfile
FROM node:22-alpine
RUN apk update --no-cache
```

### What the Dockerfile Does

1. **Base Image**: Uses `node:22-alpine` as the base image
   - This is the official Node.js version 22 image built on Alpine Linux 3.23
   - Alpine Linux is a security-oriented, lightweight Linux distribution
   - The image includes Node.js v22.21.1 and npm

2. **Package Manager Update**: Attempts to update the Alpine package index with `apk update --no-cache`
   - `apk` is the Alpine Package Keeper, Alpine Linux's package manager
   - `update` refreshes the package index from remote repositories
   - `--no-cache` flag prevents caching of the package index locally

### Build Status

**Build Result**: ❌ **FAILS**

The Docker build encounters TLS errors when attempting to fetch the Alpine package repository index:

```
WARNING: fetching https://dl-cdn.alpinelinux.org/alpine/v3.23/main/x86_64/APKINDEX.tar.gz: TLS: unspecified error
WARNING: fetching https://dl-cdn.alpinelinux.org/alpine/v3.23/community/x86_64/APKINDEX.tar.gz: TLS: unspecified error
ERROR: failed to build: failed to solve: process "/bin/sh -c apk update --no-cache" did not complete successfully: exit code: 2
```

### Issue Details

The build failure is caused by TLS connectivity issues when the Alpine package manager attempts to connect to the Alpine package repositories. This appears to be a network or environment-specific issue where:

- The base `node:22-alpine` image downloads and runs successfully
- Network connectivity to Docker Hub works properly
- However, TLS connections from within the Alpine container to `dl-cdn.alpinelinux.org` fail

### Workarounds

If you need to use Alpine Linux packages, consider these alternatives:

1. **Skip the update step**: If you don't need to install additional packages, remove the `RUN apk update` line
2. **Use a different base image**: Consider using a Debian-based Node image (`node:22`) if Alpine-specific features aren't required
3. **Pre-cached images**: Use pre-built images that already have the packages you need

### Building and Testing

To reproduce the issue:

```bash
docker build -t cca-docker-alpine-test .
```

To test just the base image (which works):

```bash
docker run --rm node:22-alpine node --version
```
