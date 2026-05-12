# Base Image
FROM ubuntu

RUN apt-get update 
RUN apt install -y curl
RUN curl -sL https://deb.nodesource.com/setup_18.x -o /tmp/nodesource_setup.sh
RUN bash /tmp/nodesource_setup.sh
RUN apt install -y nodejs

# Copying the source code to docker image
COPY index.js /home/app/index.js
COPY package-lock.json /home/app/package-lock.json
COPY package.json /home/app/package.json

WORKDIR /home/app/

RUN npm install

# after this, we can run the application using the command below
# docker build -t myApp .
#docker  images 
# docker run -it myApp


# what we did
# we created an image of this node application and we can run this image in any environment that has docker installed. This is the beauty of docker, it allows us to create a consistent environment for our application regardless of where it is run.
# we can also push this image to a docker registry like docker hub and then pull it from there in any environment. This is how we can deploy our application using docker.
# this image contains all the dependencies and the code for our application, so we can run it in any environment without worrying about the underlying infrastructure.