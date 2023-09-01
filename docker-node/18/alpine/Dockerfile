FROM node:18.17.1-alpine3.18

LABEL org.opencontainers.image.authors="skumail@folio3.com"

ENV NPM_CONFIG_PREFIX=/home/node/.npm-global

ENV PATH=$PATH:/home/node/.npm-global/bin

RUN apk add --no-cache openjdk17-jdk

USER node

RUN npm install -g --acceptsuitecloudsdklicense @oracle/suitecloud-cli

WORKDIR /usr/src/app

ENTRYPOINT ["suitecloud"]

CMD ["-h"]