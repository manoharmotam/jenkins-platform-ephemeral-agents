FROM local/jenkins-agent-base:1.0

USER root

ARG TARGETARCH=arm64

RUN set -eux; \
    case "${TARGETARCH}" in \
      arm64) AWS_ARCH="aarch64" ;; \
      amd64) AWS_ARCH="x86_64" ;; \
      *) echo "Unsupported architecture: ${TARGETARCH}"; exit 1 ;; \
    esac; \
    curl -fsSL \
      "https://awscli.amazonaws.com/awscli-exe-linux-${AWS_ARCH}.zip" \
      -o /tmp/awscliv2.zip; \
    unzip -q /tmp/awscliv2.zip -d /tmp; \
    /tmp/aws/install; \
    rm -rf /tmp/aws /tmp/awscliv2.zip; \
    aws --version

USER jenkins
