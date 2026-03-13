FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install && npm install -g typescript

COPY prisma ./prisma
RUN npx prisma generate

COPY tsconfig.json ./
COPY src ./src

RUN npx tsc -b

CMD ["node", "dist/index.js"]
