FROM node:11.1-alpine

# Install vue cli and Yarn
RUN apk update \
    && apk add --no-cache \
        yarn \
        bash \
    && yarn --version \
    && yarn global add @vue/cli