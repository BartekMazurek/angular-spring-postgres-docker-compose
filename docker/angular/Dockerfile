FROM node:18 as build

WORKDIR /app

COPY app_angular/package*.json ./

RUN npm install -g npm@latest

COPY app_angular/. ./

RUN npm install
RUN npm run build

FROM nginx:latest

COPY --from=build /app/dist/app_angular /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
