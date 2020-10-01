FROM openjdk:11.0.8-jdk-buster
LABEL maintainer="Folio3"

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -

WORKDIR /pwd

RUN apt-get update -qq && apt-get install -qq --no-install-recommends \
  nodejs \
  && rm -rf /var/lib/apt/lists/* \
  && npm -g config set user root \
  && npm install -g @oracle/suitecloud-cli

VOLUME ["/root", "/pwd"]

ENTRYPOINT ["suitecloud"]
CMD ["-h"]