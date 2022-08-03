# Temp container to execute "npm run build for creating the build folder"
FROM node:alpine as builder 
WORKDIR '/app'
COPY package.json . 
RUN npm install
COPY . .
RUN npm run build 

# Second container to run nginx Production Server 
FROM nginx 
COPY --from=builder /app/build /usr/share/nginx/html 