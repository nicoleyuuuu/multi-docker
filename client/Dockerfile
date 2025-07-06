# base image
FROM node:16-alpine as builder

# install dependencies
WORKDIR /app
COPY package.json ./
RUN npm install

# technically this could be removed if we are using docker volumes
# but if we decided not to use docker volumes or use docker prod instead, we still need it
COPY . .

# after this command, there will be a folder callted build got created, holding everything that is built
RUN npm run build

FROM nginx 
EXPOSE 3000
COPY ./nginx/default.conf /ect/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html