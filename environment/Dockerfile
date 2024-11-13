# hash:sha256:7ebd9693866d4599d46864211fca72f2d9800fabf432a12edd46e93ed0bdc398
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/pytorch-cpu-only:2.4.0

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip3 install -U --no-cache-dir \
    hdmf-zarr==0.9.0 \
    ipympl==0.9.4 \
    pydmd==2024.11.1 \
    pyro-ppl==1.9.1 \
    spikeinterface[full,widgets]==0.101.2 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@5543aa88f3585200e4dc896c1a366de3803c0166#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@2fbd35ee5a28d071ad6160ffbf10579506b58a17#egg=aind-dynamic-foraging-data-utils

COPY postInstall /
RUN /postInstall
