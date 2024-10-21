# hash:sha256:3119bd2f490e9e9c3586ab8547dbb157ec8b941d8e2383c5bb88e3dafa9f1f64
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/jupyterlab:3.6.1-miniconda4.12.0-python3.9-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip3 install -U --no-cache-dir \
    ipympl==0.9.4 \
    pyro-ppl==1.9.1 \
    torch==2.5.0 \
    torchvision==0.20.0 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@769b76f66fe63a46af105f106ed367b025722656#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@719057be98436feff33fb2c034c7ee180e9c8d7d#egg=aind-dynamic-foraging-data-utils

COPY postInstall /
RUN /postInstall
