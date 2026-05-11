<<<<<<< HEAD
# Frontend Dockerfile
FROM nginx:alpine

# Copy frontend files to nginx's default serve directory
COPY . /usr/share/nginx/html

# Create a startup script that injects environment variables at runtime
RUN echo '#!/bin/sh' > /docker-entrypoint.d/40-inject-env.sh && \
    echo 'cat > /usr/share/nginx/html/env.js << EOF' >> /docker-entrypoint.d/40-inject-env.sh && \
    echo 'window._env_ = { API_URL: "${API_URL}" };' >> /docker-entrypoint.d/40-inject-env.sh && \
    echo 'EOF' >> /docker-entrypoint.d/40-inject-env.sh && \
    chmod +x /docker-entrypoint.d/40-inject-env.sh

# Inject env.js script tag into index.html
RUN sed -i 's|</head>|<script src="/env.js"></script></head>|' /usr/share/nginx/html/index.html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
=======
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 5000
CMD ["node", "server.js"]
>>>>>>> 4e9f7a652adff2174ea54b7c496581feb69e2a0e
