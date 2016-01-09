FROM ubuntu:latest

RUN groupadd -r -g 1000 mongodb && useradd -r -g mongodb -u 1000 mongodb

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
RUN echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-3.0.list

RUN apt-get update 
RUN apt-get install -y mongodb-org git python python3-pip build-essential curl
#RUN service mongodb start
#RUN mongod &

#RUN mkdir -p /data/db

# To manually build Node, uncomment this instead
#RUN mkdir ~/node-install && cd ~/node-install
#RUN curl http://nodejs.org/dist/node-latest.tar.gz | tar xz --strip-components=1
#RUN ./configure --prefix=/opt/node && make && make install
#RUN rm -rf ~/node-install

# Install pre-built Node 0.10.22
RUN mkdir /opt/node && cd /opt/node
RUN curl http://nodejs.org/dist/v0.10.22/node-v0.10.22-linux-x64.tar.gz | tar xz --strip-components=1

#RUN npm install -g yo bower grunt-cli generator-meanjs express
#RUN alias python=python3

EXPOSE 80
EXPOSE 27017

#RUN echo "\n##############################\n1. Create a new user with adduser, 'su' into that user.\n2. 'yo meanjs' to scaffold your app in the current directory.\n3. Start mongo in the background (e.g. 'mongod &')\n##############################\n"

#USER mongodb
#RUN /usr/bin/mongod --config=/opt/apps/mongodb/mongod.conf
#CMD ["/usr/bin/mongod", "--config", "/opt/apps/mongodb/mongod.conf", "&"]
#ENTRYPOINT ["/usr/bin/mongod", "--config", "/opt/apps/mongodb/mongod.conf", "&"]

