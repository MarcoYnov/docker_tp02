FROM node:20 as base
WORKDIR /app
COPY ../package*.json .
COPY ../tsconfig.json .
RUN npm i
COPY ../.env .
COPY ../index.ts .

FROM base as build
RUN npm run build

FROM build as development
CMD [ "npm", "run", "develop" ]

FROM build as production
RUN npm install --omit=devDependencies
CMD ["npm", "run", "start"]
