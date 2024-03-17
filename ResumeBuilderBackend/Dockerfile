FROM node:alpine

WORKDIR /app

RUN apt-get install git -y 

RUN cd /app && git clone -b master https://github.com/SaiGovardhana/ResumeBuilderAngular.git

RUN npm install --force

RUN npm i -g typescript ng

RUN tsc

EXPOSE 4292

CMD ["nohup","npm","start"]