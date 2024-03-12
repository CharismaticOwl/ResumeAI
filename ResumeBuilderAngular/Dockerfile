FROM node:alpine as BUILDIMAGE

WORKDIR /app

COPY . /app

RUN npm install --force

RUN npm i -g ng @angular/cli

RUN ng build

EXPOSE 4200

CMD ["nohup","npm","start"]