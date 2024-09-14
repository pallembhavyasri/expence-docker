#node 20 docker image 
FROM node:20 
#.15.0-alpine3.20
#expose the port 8080
EXPOSE 8080
#to access the db_host with mysl container
ENV DB_HOST=mysql
RUN useradd expense 
RUN mkdir /opt/server
RUN chown expense:expense -R /opt/server
# RUN addgroup -S expense && adduser -S expense -G expense \
#     && mkdir /opt/server \
#     && chown expense:expense -R /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js /opt/server/
RUN npm install
# USER expense
# EXPOSE 8081
CMD [ "node","index.js" ]