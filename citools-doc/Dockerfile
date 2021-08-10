FROM bscpm/citools

RUN apt-get update && apt-get install -y \
    curl \
    doxygen \
    graphviz \
    python-sphinx \
    texlive-latex-extra \
    texlive-fonts-recommended \
    latexmk \
    && rm -rf /var/lib/apt/lists/*

# the 'pandoc' package from repositories does not provide 'man' format support
ARG pandoc_version=2.14.1
ARG pandoc_package=pandoc-2.14.1-1-amd64.deb
RUN curl -L -o /tmp/${pandoc_package} \
        https://github.com/jgm/pandoc/releases/download/${pandoc_version}/${pandoc_package} && \
    dpkg -i /tmp/${pandoc_package} && \
    rm /tmp/${pandoc_package}
