# hash:sha256:f91973dd30b9cb261d208254ed62b9faf09ca968ca94eca501311698b1de4729
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/jupyterlab:3.6.1-miniconda4.12.0-python3.9-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip3 install -U --no-cache-dir --upgrade-strategy=only-if-needed \
    ipympl==0.9.4 \
    pyro-ppl==1.9.1 \
    torch==2.5.0 \
    torchvision==0.20.0 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@769b76f66fe63a46af105f106ed367b025722656#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@719057be98436feff33fb2c034c7ee180e9c8d7d#egg=aind-dynamic-foraging-data-utils

COPY postInstall /
RUN /postInstall
