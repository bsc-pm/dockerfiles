FROM bscpm/citools

RUN apt-get update && apt-get install -y \
    curl \
    doxygen \
    graphviz \
    python3-sphinx \
    python3-sphinxcontrib-mermaid \
    texlive-latex-extra \
    texlive-fonts-recommended \
    latexmk \
    pandoc \
    && rm -rf /var/lib/apt/lists/*
