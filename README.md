# Docker Alpine Node.js Image

This repository contains a minimal Dockerfile for creating a Node.js container based on Alpine Linux.

## Dockerfile Description

The Dockerfile uses the official `node:22-alpine` base image, which provides:

- **Base OS**: Alpine Linux - A lightweight Linux distribution ideal for containers
- **Node.js Version**: v22 (current release) - Modern JavaScript runtime environment
- **Package Manager**: npm - Node Package Manager for managing JavaScript dependencies
- **Image Size**: Optimized for minimal footprint using Alpine Linux

> **Note**: Version numbers may vary as the base image is updated. Current versions at time of writing: Alpine Linux v3.23, Node.js v22.21.1, npm v10.9.4

### Features

- **Lightweight**: Alpine Linux-based images are significantly smaller than standard Debian/Ubuntu-based images
- **Secure**: Alpine Linux has a smaller attack surface due to its minimal design
- **Node.js Ready**: Comes pre-installed with Node.js and npm for immediate JavaScript/TypeScript development

## Building the Image

To build the Docker image:

```bash
docker build -t cca-docker-alpine .
```

## Running the Container

To verify the installation and run Node.js commands:

```bash
# Check Node.js version
docker run --rm cca-docker-alpine node --version

# Check npm version
docker run --rm cca-docker-alpine npm --version

# Run an interactive shell
docker run --rm -it cca-docker-alpine sh
```

## Use Cases

This image is suitable for:
- Running Node.js applications in production with minimal overhead
- Creating microservices with Node.js
- Building JavaScript/TypeScript applications
- Serving as a base image for more complex Node.js projects

## Image Details

- **Architecture**: x86_64
- **Total Size**: ~120 MB (base image)
- **Shell**: sh (Alpine's default shell)
