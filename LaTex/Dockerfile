FROM ubuntu:latest

RUN apt-get update \
    && apt-get install -y \
    python3 \
    git \
    wget \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ADD texlive.profile /texlive.profile

# Install LaTeX
RUN wget http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz
RUN tar xvf install-tl-unx.tar.gz \
    && cd install-tl* \
    && ./install-tl -no-gui -repository http://mirror.ctan.org/systems/texlive/tlnet/ --profile=/texlive.profile

RUN /usr/local/texlive/latest/bin/x86_64-linux/tlmgr path add

RUN mkdir -p /workdir
WORKDIR /workdir

CMD ["/bin/bash"]
