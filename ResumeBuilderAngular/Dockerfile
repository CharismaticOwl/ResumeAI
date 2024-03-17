FROM node:alpine

WORKDIR /app

RUN apk add git -y 

RUN cd /app && git clone -b master https://github.com/SaiGovardhana/ResumeBuilderBackend.git

RUN npm install --force

RUN npm i -g ng @angular/cli

RUN npm run build

EXPOSE 4200

CMD ["nohup","npm","start"]