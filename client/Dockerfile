FROM node:19-alpine3.15
WORKDIR /app

RUN rm -rf node_modules
RUN rm -f package-lock.json
RUN npm cache clean --force
COPY package*.json ./
# RUN npm install -g create-react-app
# RUN npm install -g npm@9.2.0

RUN npm install
# RUN npm install -g create-react-app
COPY . .
RUN npm run build
RUN npm install -g serve
EXPOSE 3000
CMD [ "serve", "-s", "build", "-l", "3000" ]
# CMD [ "npm", "start"]