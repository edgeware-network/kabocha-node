FROM  decentration/kabocha:0.9.8 as builder

LABEL maintainer="kabocha-dev"
ARG RUST_VERSION=1.53.0
ARG PROFILE=release
ARG KABOCHA_GIT_REPO="https://github.com/edgeware-network/kabocha-node.git"
ARG DOT_GIT_REPO="https://github.com/paritytech/polkadot.git"
ARG GIT_BRANCH="polkadot-v0.9.8-docker"


#Build Kylin-node
#RUN git clone --recursive ${KABOCHA_GIT_REPO}

WORKDIR /builds/kabocha-node
RUN curl -0 https://raw.githubusercontent.com/centrifuge/polkadot/chachacha/node/service/res/rococo-chachacha.json -o rococo-chachacha.json
#RUN git checkout ${GIT_BRANCH}
#RUN git submodule update --recursive --remote
#RUN cargo build --${PROFILE}

RUN cp builds/kabocha-node/target/${PROFILE}/parachain-collator /builds/kabocha-node

EXPOSE 30333-30343 9933-9960 8080 300
