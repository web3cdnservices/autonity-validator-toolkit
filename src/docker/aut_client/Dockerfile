FROM ubuntu:23.10 as builder

WORKDIR /app

FROM ubuntu:23.10
RUN set -x && apt-get update && apt-get install -y \
    ca-certificates bash curl wget bc jq pipx python3 git  && \
    rm -rf /var/lib/apt/lists/*

#RUN wget https://github.com/gochain/web3/releases/download/v0.2.90/web3_linux
RUN curl -LSs https://raw.githubusercontent.com/gochain/web3/master/install.sh | sh
#RUN mv web3_linux /usr/local/bin/web3
RUN chmod +x /usr/local/bin/web3

RUN pipx install --force 'https://github.com/autonity/aut/releases/download/v0.3.0.dev1/aut-0.3.0.dev1-py3-none-any.whl'

CMD sleep infinity
