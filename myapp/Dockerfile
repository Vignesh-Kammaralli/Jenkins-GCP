#stage 1
FROM node:latest as node
WORKDIR /app
COPY . ./
RUN npm cache clean --force
RUN rm -rf node_modules
RUN npm install
RUN npm run build --prod
#stage 2
FROM nginx:alpine
COPY --from=node /app/dist/myapp /usr/share/nginx/html

