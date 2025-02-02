FROM alpine:3.21.2

# Enables customized options using environment variables
ENV OSRM_BACKEND='http://localhost:5000'
ENV OSRM_CENTER='38.8995,-77.0269'
ENV OSRM_ZOOM='13'
ENV OSRM_LANGUAGE='en'
ENV OSRM_LABEL='Car (fastest)'
ENV OSRM_MAPBOX_TOKEN='pk.eyJ1IjoibXNsZWUiLCJhIjoiclpiTWV5SSJ9.P_h8r37vD8jpIH1A6i1VRg'
ENV NOMINATIM_URL='https://nominatim.openstreetmap.org'

# Copy package.json
RUN mkdir -p /src
WORKDIR /src
COPY package.json /src

# Install app dependencies
RUN apk add --no-cache sed nodejs npm && \
    npm install

# Create app directory
COPY . /src

# Expose the application port
EXPOSE 9966

# Run App
CMD ["npm", "start"]
