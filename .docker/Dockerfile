FROM node:20 as base
WORKDIR /app
COPY ../package*.json .
RUN npm i

FROM base as production
COPY ../.env .
COPY ../index.ts .