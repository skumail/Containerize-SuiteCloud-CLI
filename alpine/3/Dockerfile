FROM alpine:3.12.0

LABEL maintainer="Folio3"

WORKDIR /pwd

RUN apk add --no-cache openjdk11-jdk nodejs npm\
  && npm -g config set user root \ 
  && npm install -g @oracle/suitecloud-cli

VOLUME ["/root", "/pwd"]

ENTRYPOINT ["suitecloud"]

CMD ["-h"]