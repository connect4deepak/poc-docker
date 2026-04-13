FROM node:16 as build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM node:16
WORKDIR /app
COPY --from=build-stage /app/ .
EXPOSE 3000
CMD ["node", "server.js"]