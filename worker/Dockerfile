FROM node:16-alpine

# install dependencies
WORKDIR /app
COPY package.json .
RUN npm install

# technically this could be removed if we are using docker volumes
# but if we decided not to use docker volumes or use docker prod instead, we still need it
COPY . .

# default command 
# in the package.js, we loaded "dev": "NODE_ENV=development nodemon"
# dev represented the command to run
# nodemon is a command line tool that can used to automatically reload the code change in a project
# work will with volume
CMD ["npm", "run", "start"]