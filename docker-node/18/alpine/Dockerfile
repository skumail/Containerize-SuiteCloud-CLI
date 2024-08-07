FROM node:18.20.4-alpine3.20

LABEL org.opencontainers.image.authors="skumail@folio3.com"

ENV NPM_CONFIG_PREFIX=/home/node/.npm-global

ENV PATH=$PATH:/home/node/.npm-global/bin

RUN apk add --no-cache dbus openjdk17-jdk

RUN dbus-uuidgen --ensure

USER node

RUN npm install -g --acceptsuitecloudsdklicense @oracle/suitecloud-cli

WORKDIR /usr/src/app

ENTRYPOINT ["suitecloud"]

CMD ["-h"]