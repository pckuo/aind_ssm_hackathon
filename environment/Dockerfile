# hash:sha256:b6bfe6cb8d10e64bb0fce6736ac5f683813dc59e075ce01c758bb95a7f0be6e6
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/pytorch-cpu-only:2.4.0

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip3 install -U --no-cache-dir \
    dynamax[notebooks]==0.1.4 \
    ipympl==0.9.4 \
    pyro-ppl==1.9.1 \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-basic-analysis.git@5543aa88f3585200e4dc896c1a366de3803c0166#egg=aind-dynamic-foraging-basic-analysis \
    -e git+https://github.com/AllenNeuralDynamics/aind-dynamic-foraging-data-utils.git@2fbd35ee5a28d071ad6160ffbf10579506b58a17#egg=aind-dynamic-foraging-data-utils

COPY postInstall /
RUN /postInstall
