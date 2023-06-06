FROM mcr.microsoft.com/vscode/devcontainers/rust:1-bullseye

# Install LLVM dependencies
RUN apt-get -qq update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -qqy --no-install-recommends fuse \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*
