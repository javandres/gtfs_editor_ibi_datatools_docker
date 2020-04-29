FROM node:10

ENV VERSION=v2.0.0

RUN apt-get update && \
    apt-get install -y --no-install-recommends gettext-base && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN npm i -g serve

RUN git clone https://github.com/ibi-group/datatools-ui.git /opt/datatools-ui

WORKDIR /opt/datatools-ui

ADD ./config/*.yml /config/

RUN yarn

COPY /config/settings.yml /opt/datatools-ui/configurations/default/settings.yml

EXPOSE 9966

CMD envsubst < /config/env.yml > /opt/datatools-ui/configurations/default/env.yml && \
    $(npm bin)/mastarm build --env production && serve -p 9966
