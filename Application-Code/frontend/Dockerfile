#FROM node:14
#WORKDIR /usr/src/app
#COPY package*.json ./
#RUN npm install
#COPY . .
#CMD [ "npm", "start" ]


FROM node:14 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Step 2: Serve the build with Nginx
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
