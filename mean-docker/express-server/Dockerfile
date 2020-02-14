FROM node:6
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
COPY package.json /usr/src/app
RUN npm install
Copy . /usr/src/app
EXPOSE 3000
CMD ["npm","start"]

