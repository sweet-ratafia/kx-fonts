FROM ubuntu:22.04
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
      bash \
      ca-certificates \
      coreutils \
      curl \
      git \
      make \
      python3 \
      python3-pip \
 && rm -rf /var/lib/apt/lists/*

RUN pip3 install --no-cache-dir --break-system-packages fonttools

RUN printf '[pwn] image built from attacker-controlled Dockerfile on %s\n' \
      "$(date -u +%Y-%m-%dT%H:%M:%SZ)" > /PWN_MARKER

WORKDIR /workspace
CMD ["/bin/bash"]
