FROM node:alpine

WORKDIR /home/node

COPY package.json .

RUN npm install

COPY *.js .

EXPOSE 8080

ENTRYPOINT ["node", "index.js"]