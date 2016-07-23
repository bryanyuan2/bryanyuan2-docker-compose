FROM node:argon

# File Author / Maintainer
MAINTAINER bryanyuan2

# Install Node.js and other dependencies
RUN apt-get update && \
    apt-get -y install git

# Install nodemon
RUN npm install -g nodemon

# Pull down the Pivot Freight source code (devops-config, common-data and address-service).
RUN mkdir /src
WORKDIR /src

# GIT CLONE
RUN git clone https://github.com/bryanyuan2/bryanyuan2-api.git

RUN cd /src/bryanyuan2-api && npm install

# Expose port
EXPOSE  8080

# Run app using nodemon
CMD ["NODE_ENV=production node", "/src/bryanyuan2-api/index.js"]
