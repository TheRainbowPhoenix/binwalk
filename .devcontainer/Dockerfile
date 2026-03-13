# Minimal GitHub Codespaces image for this repository.
FROM ghcr.io/therainbowphoenix/binwalk:master

# Switch to root to allow package installation and set the default user
USER root

# Update package list and install Python 3 and pip
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends \
        python3 \
        python3-pip \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Codespaces mounts the repository under /workspaces/<repo-name>.
WORKDIR /workspaces/binwalk