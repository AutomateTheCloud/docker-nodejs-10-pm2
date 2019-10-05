##-------------------------------------------------------------------------------------------------
# name:        nodejs-10-pm2
# description: Node.js 10 (with PM2)
# tag:         10.16.3
##-------------------------------------------------------------------------------------------------
FROM node:10.16.3-buster
MAINTAINER David Singer <david.singer@automatethe.cloud>

# Update Image
RUN apt-get update && \
    apt-get upgrade -y && \
    rm -rf /var/lib/apt/lists/*

# Install pm2
RUN npm install pm2 -g

# Update Kernel Parameters for Watcher Support
COPY resources/local.conf /etc/sysctl.d/local.conf

CMD ["pm2-runtime", "start", "pm2.json"]
