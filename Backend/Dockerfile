FROM node:14-alpine as build

WORKDIR /society/Backend/
COPY package.json ./
RUN npm install
COPY . ./
RUN npm run build

# Serve the app using nginx
FROM nginx:alpine
COPY --from=Frontend/myapp/public/index.html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
