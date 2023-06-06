FROM mcr.microsoft.com/vscode/devcontainers/rust:1-bullseye

# Install LLVM dependencies
RUN apt-get -qq update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -qqy --no-install-recommends \
        gnupg2 curl wget strace ca-certificates apt-transport-https man-db \
        autoconf automake cmake dpkg-dev file make patch libc6-dev git fuse \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*
