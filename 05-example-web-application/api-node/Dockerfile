FROM node:14

# Create and change to the app directory
WORKDIR /usr/src/app

# Copy application dependency manifests
COPY package*.json ./

# Install production dependencies
RUN npm install 

# Copy the rest of the application code
COPY ./src .

# Expose the application port
EXPOSE 3000

# Start the application
CMD [ "node", "index.js" ]