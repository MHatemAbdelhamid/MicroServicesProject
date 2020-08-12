FROM node:12
# Create app directory
WORKDIR /usr/src/app
# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./
RUN npm ci 
RUN npm uninstall bcrypt
RUN npm i node-pre-gyp
RUN npm i bcrypt@latest --save

# Bundle app source
COPY . .
EXPOSE 8080
CMD [ "npm", "run", "prod" ]
