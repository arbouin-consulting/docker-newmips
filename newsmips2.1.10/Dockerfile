FROM node:carbon-alpine

RUN mkdir -p /srv/app \
    && apk update \
    && apk add ca-certificates wget unzip \
    && update-ca-certificates
WORKDIR /srv/app

RUN wget https://github.com/newmips/newmips/archive/v2.1.10.zip \
    && unzip v2.1.10.zip -d /srv/app/ \
    && rm -rf v2.1.10.zip
    && apk add --no-cache --virtual .node-yarn nodejs yarn \
    && yarn install


RUN cd /usr/src/app/structure/template && npm install

EXPOSE 3000

CMD ["yarn", "start"]
