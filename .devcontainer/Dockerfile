# Find the Dockerfile at this URL
# https://github.com/Azure/azure-functions-docker/blob/dev/host/4/bullseye/amd64/python/python311/python311-core-tools.Dockerfile
# with open vpn for vnet access
FROM mcr.microsoft.com/azure-functions/python:4-python3.11-core-tools

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && curl -sL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get -y install \
    git \
    openssh-client \
    less \
    unzip \
    iproute2 \
    procps \
    curl \
    apt-transport-https \
    gnupg2 \
    lsb-release \
    #
    # Install coretools package for debian-11/bullseye from linux software repository
    && curl -sSL -O https://packages.microsoft.com/config/debian/11/packages-microsoft-prod.deb \
    && dpkg -i packages-microsoft-prod.deb \
    && rm packages-microsoft-prod.deb \
    && apt-get update  \    
    && apt-get install -y cifs-utils \
    && apt-get install -y nodejs \
    && apt-get autoremove -y \
    && apt-get -y install --no-install-recommends openvpn \
    && apt-get clean -y \
    && echo 'OPENVPN_CONFIG=""' >> /etc/environment \
    && echo "unset OPENVPN_CONFIG" | tee -a /etc/bash.bashrc > /etc/profile.d/999-unset-openvpn-config.sh \
    && if [ -d "/etc/zsh" ]; then echo "unset OPENVPN_CONFIG" >> /etc/zsh/zshenv; fi

