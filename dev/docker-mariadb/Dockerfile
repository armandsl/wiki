# -- DEV DOCKERFILE --
# -- DO NOT USE IN PRODUCTION! --

FROM node:10-alpine@sha256:dc98dac24efd4254f75976c40bce46944697a110d06ce7fa47e7268470cf2e28
LABEL maintainer "requarks.io"

RUN apk update && \
    apk add bash curl git python make g++ nano openssh gnupg --no-cache && \
    mkdir -p /wiki

WORKDIR /wiki
COPY package.json .
RUN yarn --silent
COPY ./dev/docker-mariadb/init.sh ./init.sh

ENV dockerdev 1
ENV DEVDB mariadb

EXPOSE 3000

CMD ["tail", "-f", "/dev/null"]
