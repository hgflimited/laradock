FROM haskell
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update -q && apt-get install -qy \
 curl jq \
 texlive-full \
 python-pygments gnuplot \
 make git \
 && rm -rf /var/lib/apt/lists/*

COPY ./src /app
WORKDIR /app/pandocAPI
RUN stack build --install-ghc

CMD ["stack exec pandocAPI-exe"]
