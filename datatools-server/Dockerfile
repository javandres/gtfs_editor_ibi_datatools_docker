FROM maven:3.6.3-openjdk-11

ENV VERSION=v2.0.1

RUN apt-get update
RUN apt-get install -y --no-install-recommends git


RUN mvn -v

RUN git clone https://github.com/ibi-group/datatools-server.git /opt/datatools-server

WORKDIR /opt/datatools-server

VOLUME /root/.m2

ADD ./config/* /config/

COPY /config/env.yml /opt/datatools-server/configurations/default/env.yml
COPY /config/server.yml /opt/datatools-server/configurations/default/server.yml
COPY /config/auth.pem /opt/datatools-server/configurations/auth.pem

RUN mvn package -Dmaven.test.skip=true

EXPOSE 4000

CMD java -jar "target/dt-$(git describe --always).jar"
