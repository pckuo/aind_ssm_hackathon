# hash:sha256:17608ea72a0528a27505d1be6c9a12e594607a20713a68ff745c7ae49b26e21f
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/pytorch-cpu-only:2.4.0

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        g++=4:11.2.0-1ubuntu1 \
        gcc=4:11.2.0-1ubuntu1 \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install -U --upgrade-strategy=only-if-needed \
    hdmf-zarr==0.9.0 \
    ipympl==0.9.4 \
    pydmd==2024.11.1 \
    pyro-ppl==1.9.1 \
    spikeinterface[full,widgets]==0.101.2 \
    wavpack-numcodecs==0.2.1 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@5543aa88f3585200e4dc896c1a366de3803c0166#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@2fbd35ee5a28d071ad6160ffbf10579506b58a17#egg=aind-dynamic-foraging-data-utils

COPY postInstall /
RUN /postInstall
