FROM ubuntu:latest

# Install Node.js
RUN apt-get update
RUN apt-get install -y build-essential curl

# To manually build Node, uncomment this instead
#RUN mkdir ~/node-install && cd ~/node-install
#RUN curl http://nodejs.org/dist/node-latest.tar.gz | tar xz --strip-components=1
#RUN ./configure --prefix=/opt/node && make && make install
#RUN rm-rf ~/node-install

# Install pre-built Node 0.10.22
RUN mkdir /opt/node && cd /opt/node
RUN curl http://nodejs.org/dist/v0.10.22/node-v0.10.22-linux-x64.tar.gz | tar xz --strip-components=1

RUN echo "export PATH=$PATH:/opt/node/bin" >> ~/.bashrc
RUN . ~/.bashrc

# Run the node server
CMD ["node", "/opt/apps/index.js"]

EXPOSE 80

