# hash:sha256:a30277006a85896ffd8f9b8105fe8f850307d20424937e34ea11cfd6c0c89d47
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/jupyterlab:3.0.9-miniconda4.9.2-python3.8-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip3 install -U --no-cache-dir \
    ipykernel \
    ipympl \
    torch \
    torchvision \
    torchaudio \
    pyro-ppl


COPY postInstall /
RUN /postInstall
