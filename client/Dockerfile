FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.config /etc/nginx/conf.d/default.conf
COPY --
CMD ["npm","run","start"]