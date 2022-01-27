FROM node:15.4 as build
WORKDIR /app
COPY package*.json .
RUN npm install
COPY . .
 

FROM nginx:1.19
 
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY --from=build /app/dist/online-test/ /usr/share/nginx/html
