FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install && npm install -g typescript

COPY prisma ./prisma
RUN npx prisma generate

COPY tsconfig.json ./
COPY src ./src

RUN npx tsc -b

EXPOSE 3002

CMD npx prisma migrate deploy && node dist/index.js
