# GTFS Online Editor

This repo contains the Dockerfiles of [Conveyal Data Tools]([https://data-tools-docs.ibi-transit.com/en/latest/](https://data-tools-docs.ibi-transit.com/en/latest/)) for Quick and easy GTFS editing, which is composed of two parts:
- a [backend](https://github.com/ibi-group/datatools-serverd)
- a [UI](https://github.com/ibi-group/datatools-ui)

## Run on your system
Quickstart:
```
git clone https://github.com/javandres/gtfs_editor_ibi_datatools_docker
cd gtfs_editor_ibi_datatools_docker
cp ./datatools-server/config/env.yml.tmp ./datatools-server/config/env.yml
cp ./datatools-server/config/server.yml.tmp ./datatools-server/config/server.yml
cp ./datatools-ui/config/env.yml.tmp ./datatools-ui/config/env.yml
cp ./datatools-ui/config/settings.yml.tmp ./datatools-ui/config/settings.yml
```
Edit the configuration files and view [https://data-tools-docs.ibi-transit.com/en/latest/dev/deployment/](https://data-tools-docs.ibi-transit.com/en/latest/dev/deployment/) for documentation:

```
docker-compose up
```

Then navigate to [http://localhost:8081/](http://localhost:8081/)

