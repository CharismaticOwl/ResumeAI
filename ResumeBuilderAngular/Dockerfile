FROM node:alpine

WORKDIR /app

COPY . /app

RUN npm install --force

RUN npm i -g ng @angular/cli

RUN npm run build

EXPOSE 4200

CMD ["nohup","npm","start"]