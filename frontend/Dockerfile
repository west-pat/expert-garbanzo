FROM node:15.14.0-alpine3.10

RUN mkdir -p hslolfrontend 

COPY ./ /hslolfrontend

RUN apk update && \
    apk add mailcap && \
    apk add util-linux && \
    rm /var/cache/apk/* && \
    npx browserslist@latest --update-db

RUN cd /hslolfrontend &&\
    npm install ol && \
    npm install --save-dev parcel-bundler &&\
    npm run build

WORKDIR ./hslolfrontend/dist

ENTRYPOINT ["/usr/local/bin/npm", "start"]
