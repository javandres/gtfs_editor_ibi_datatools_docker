FROM node:14

ENV VERSION=v5.0.0

RUN apt-get update && \
    apt-get install -y --no-install-recommends gettext-base && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN npm i -g serve

#RUN  git clone -b 'v4.1.0' --single-branch https://github.com/wkulesza/datatools-ui.git /opt/datatools-ui
RUN git clone -b 'dev' --single-branch https://github.com/ibi-group/datatools-ui.git /opt/datatools-ui
#RUN git clone -b 'dev' --single-branch https://github.com/wkulesza/datatools-ui.git /opt/datatools-ui
WORKDIR /opt/datatools-ui

#current synchronised branch
RUN git checkout b240cb6f0a8d809f18bae8315a610e8af921ca0a

ADD ./config/*.yml /config/

RUN yarn

COPY /config/settings.yml /opt/datatools-ui/configurations/default/settings.yml

EXPOSE 9966

CMD envsubst < /config/env.yml > /opt/datatools-ui/configurations/default/env.yml && \
    $(npm bin)/mastarm build --env production && serve -p 9966
