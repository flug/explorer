FROM node:10-alpine

WORKDIR /workspace

RUN apk add --no-cache --update git

COPY .  .

RUN yarn

USER node

EXPOSE 8080

ENV HOST 0.0.0.0

CMD ["yarn", "dev:devnet"]
