FROM node:alpine

USER node

RUN mkdir -p /home/node/app

WORKDIR /home/node/app

COPY --chown=node:node  ./package.json /home/node/app/package.json

RUN npm install

COPY ./ /home/node/app/

RUN npm run build

FROM nginx:latest
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=0 /home/node/app/build /usr/share/nginx/html