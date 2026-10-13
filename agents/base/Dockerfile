FROM jenkins/inbound-agent:jdk21

USER root

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       bash \
       ca-certificates \
       curl \
       git \
       jq \
       python3 \
       python3-pip \
       python3-venv \
       unzip \
       zip \
    && rm -rf /var/lib/apt/lists/*

USER jenkins
