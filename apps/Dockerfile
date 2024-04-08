ARG NODEJS_VERSION="20"

FROM one.hitachivantara.com/docker/node:${NODEJS_VERSION}-alpine AS node

RUN npm -g install npm@latest

WORKDIR /app

COPY --chown=node:node package.json package-lock.json ./
RUN npm install --frozen-lockfile && npm cache clean --force

COPY --chown=node:node index.js webpack.config.js ./
COPY --chown=node:node src/ ./src/

RUN npm run build
RUN rm -rf index.js webpack.config.js src
RUN mkdir -p -m 0770 logs && chown node:node ./logs

USER node
CMD [ "node", "server.js" ]
