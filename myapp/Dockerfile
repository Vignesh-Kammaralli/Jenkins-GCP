#stage 1
FROM node:latest as node
WORKDIR /app
COPY ./ /app
RUN npm install socket.io --save
RUN npm run-script build --prod
#stage 2
FROM nginx:alpine
COPY --from=node /app/dist/myapp /usr/share/nginx/html
