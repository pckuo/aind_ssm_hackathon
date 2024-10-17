# hash:sha256:0787036ad5c7344aeea43d912749eff2ff6465c8b50b3dae95b14c3c8e444833
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/jupyterlab:3.6.1-miniconda4.12.0-python3.9-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip3 install -U --no-cache-dir \
    ipykernel==6.29.5 \
    ipympl==0.9.4 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@769b76f66fe63a46af105f106ed367b025722656#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@719057be98436feff33fb2c034c7ee180e9c8d7d#egg=aind-dynamic-foraging-data-utils
    torch \
    torchvision \
    torchaudio \
    pyro-ppl


COPY postInstall /
RUN /postInstall
