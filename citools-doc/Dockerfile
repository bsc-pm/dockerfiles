FROM bscpm/citools

RUN apt-get update && apt-get install -y \
    curl \
    doxygen \
    graphviz \
    sphinx-doc \
    texlive-latex-extra \
    texlive-fonts-recommended \
    latexmk \
    pandoc \
    && rm -rf /var/lib/apt/lists/*
