# Base image
FROM node:18-alpine

# Set working directory
WORKDIR /ui

# Copy package.json and package-lock.json
COPY ./package*.json ./

# Remove package-lock.json and node_modules if they exist
RUN rm -rf package-lock.json node_modules

# Install dependencies
RUN yarn install

# Copy the rest of the application files
COPY . .

# Expose the port the app runs on
EXPOSE 8080

# Command to run the app
CMD ["yarn", "vite"]