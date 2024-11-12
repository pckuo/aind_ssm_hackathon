# hash:sha256:825e7c8591849663adc6b7b6d9a9fa8e68638c343544516ed4ec3cd66bab3cc5
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

RUN pip3 install -U --no-cache-dir \
    cython==3.0.11 \
    ipympl==0.9.4 \
    pyro-ppl==1.9.1 \
    seaborn==0.13.2 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@5543aa88f3585200e4dc896c1a366de3803c0166#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@2fbd35ee5a28d071ad6160ffbf10579506b58a17#egg=aind-dynamic-foraging-data-utils

COPY postInstall /
RUN /postInstall
