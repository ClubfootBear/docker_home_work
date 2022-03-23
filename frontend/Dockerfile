FROM node:14-alpine as build_front

WORKDIR /app

COPY package.json /app
COPY package-lock.json /app
RUN npm install
COPY . /app
RUN npm run build   

FROM node:14-alpine

WORKDIR /app

COPY --from=build_front /app/build /app/build
RUN npm install -g serve

CMD ["serve", "-s", "build"]


# The build folder is ready to be deployed.
# You may serve it with a static server:

#   npm install -g serve
#   serve -s build