FROM ubuntu:jammy

RUN apt-get update && apt-get install -y \
    skopeo \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT [ "skopeo", "copy", "-f", "oci", "--src-tls-verify=false", "--dest-tls-verify=false", "docker://ghcr.io/huggingface/text-generation-inference:sha-d077150", "docker://zot:5000/text-generation-inference:latest" ]