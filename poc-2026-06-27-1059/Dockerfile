FROM node:14 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM node:14
WORKDIR /app
COPY --from=build /app /app
EXPOSE 3000
CMD ["node", "server.js"]