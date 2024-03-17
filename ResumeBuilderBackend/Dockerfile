FROM node:alpine

WORKDIR /app

COPY . .

RUN npm install --force

RUN npm i -g typescript ng

RUN tsc

EXPOSE 4292

CMD ["nohup","npm","start"]