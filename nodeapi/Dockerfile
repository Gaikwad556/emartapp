FROM node:14 AS node-build
WORKDIR /usr/src/app/
COPY ./ ./nodeapi
RUN cd nodeapi && npm install

FROM node:14
WORKDIR /usr/src/app/
COPY --from=node-build /usr/src/app/nodeapi/ ./
EXPOSE 5000
CMD ["/bin/sh","-c","cd /usr/src/app/ && npm start"]
