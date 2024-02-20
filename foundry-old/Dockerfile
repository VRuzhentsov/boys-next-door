FROM node:20-alpine

ENV FOUNDRY_HOME=/home/node/app
ENV FOUNDRY_DATA=/home/node/data

RUN mkdir -p "${FOUNDRY_HOME}" \
    && chown -R node:node "${FOUNDRY_HOME}"

RUN mkdir -p "${FOUNDRY_DATA}" \
    && chown -R node:node "${FOUNDRY_DATA}"

# Set the current working directory
WORKDIR "${FOUNDRY_HOME}"

EXPOSE 30000

CMD node ${FOUNDRY_HOME}/resources/app/main.js --dataPath=${FOUNDRY_DATA}

