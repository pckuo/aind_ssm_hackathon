# hash:sha256:0cd78d9881682cf51989f36da936746e2ad41f23847a1a544034424a2c456639
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/pytorch-cpu-only:2.4.0

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip3 install -U --no-cache-dir \
    ipympl==0.9.4 \
    pydmd==2024.11.1 \
    pyro-ppl==1.9.1 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@5543aa88f3585200e4dc896c1a366de3803c0166#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@2fbd35ee5a28d071ad6160ffbf10579506b58a17#egg=aind-dynamic-foraging-data-utils

COPY postInstall /
RUN /postInstall
