# Minimal GitHub Codespaces image for this repository.
FROM ghcr.io/therainbowphoenix/binwalk:master

# Switch to root to allow package installation and set the default user
USER root

# Update package list and install Python 3 and pip
# Minimal GitHub Codespaces image for this repository.
FROM ghcr.io/therainbowphoenix/binwalk:master

# Switch to root to install packages and modify system files
USER root

# Update package list, install requested tools, and grant ubuntu passwordless sudo
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends \
        sudo \
        python3 \
        python3-pip \
        python3-venv \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* \
    && echo "ubuntu ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/ubuntu \
    && chmod 0440 /etc/sudoers.d/ubuntu

# Codespaces mounts the repository under /workspaces/<repo-name>.
WORKDIR /workspaces/binwalk

# Drop back to the non-root user for security and parity
USER ubuntu

RUN pip3 install --break-system-packages jefferson