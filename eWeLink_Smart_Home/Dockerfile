# ARG BUILD_FROM
# FROM $BUILD_FROM


FROM node:16-bullseye-slim

ENV CK_API_ENV=prod

RUN apt-get update && \
    apt-get install -y python3 build-essential && \
    ln -s /usr/bin/python3 /usr/bin/python

RUN mkdir -p /workspace/node_modules

COPY ["./dist", "./package.json", "/workspace/"]

WORKDIR /workspace

RUN npm install --production

CMD ["node", "dist/index.js"]

