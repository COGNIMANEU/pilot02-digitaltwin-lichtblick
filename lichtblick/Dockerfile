# Use official Node.js base image
FROM node:16.10

# Set working directory inside the container
WORKDIR /app

# Clone the Lichtblick repository
# Note: Git must be installed to allow git clone
RUN apt-get update && \
    apt-get install -y git && \
    git clone https://github.com/lichtblick-suite/lichtblick.git . && \
    apt-get clean

RUN corepack enable && yarn install

RUN yarn run web:build:prod

RUN npm install -g serve

# Expose the port the app will run on
EXPOSE 8080

# Start the web server
CMD ["serve", "-s", "web/.webpack", "-l", "8080"]
