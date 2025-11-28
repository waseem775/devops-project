FROM node:18

# Set working directory
WORKDIR /app

# Install create-react-app globally
RUN npm install -g create-react-app

# Create a new React app automatically (replace "myapp" if you want)
RUN create-react-app myapp

# Set working directory to the newly created app
WORKDIR /app/myapp

# Install dependencies
RUN npm install

# Start the React app
CMD ["npm", "start"]

# Expose port
EXPOSE 3000
