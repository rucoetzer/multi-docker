FROM node:14.14.0-alpine

USER node

RUN mkdir -p /home/node/app

WORKDIR /home/node/app

COPY --chown=node:node ./package.json /home/node/app/package.json

RUN npm install

COPY --chown=node:node ./ /home/node/app

CMD ["npm", "run", "start"]
