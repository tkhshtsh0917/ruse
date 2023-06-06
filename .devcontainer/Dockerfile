FROM mcr.microsoft.com/vscode/devcontainers/rust:1-bullseye

# Install LLVM dependencies
RUN apt-get -qq update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -qqy --no-install-recommends \
        gnupg2 curl wget strace ca-certificates apt-transport-https man-db \
        autoconf automake cmake dpkg-dev file make patch libc6-dev git

# Install LLVM
RUN echo "deb https://apt.llvm.org/bullseye llvm-toolchain-bullseye-15 main" > /etc/apt/sources.list.d/llvm.list \
    && wget -qO /etc/apt/trusted.gpg.d/llvm.asc https://apt.llvm.org/llvm-snapshot.gpg.key
RUN apt-get -qq update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -qqy --no-install-recommends -t \
        llvm-toolchain-bullseye-15 clang-15 clang-tidy-15 clang-format-15 lld-15 \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*
RUN for f in /usr/lib/llvm-15/bin/*; do ln -sf "$f" /usr/bin; done
