FROM node:20.11.1 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist/microservices-shop-frontend/browser /usr/share/nginx/html
