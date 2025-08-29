FROM node:19.6-alpine

# Create and change to the app directory
WORKDIR /usr/src/app

ENV NODE_ENV=production

# Copy application dependency manifests
COPY package*.json ./

# Install production dependencies
RUN --mount=type=cache,target=/usr/src/app/.npm \
    npm set cache /usr/src/app/.npm && \
    npm ci --only=production

USER node

# Copy the rest of the application code
COPY --chown=node:node ./src .

# Expose the application port
EXPOSE 3000

# Start the application
CMD [ "node", "index.js" ]