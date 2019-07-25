# Docker Configs

This are the various docker-compose configs.

## Swarm

This contains docker-compose configs for the main Docker Swarm.

[Link](./swarm)

#### Services

* InfluxDB - Metric database
* Telegraf - Metric collector
* Grafana - Visualise metrics
* MariaDB - Database for Kodi
* Kodi - Headless Kodi for media library updates
* Resilio - Phone media backups
* Transmission - Torrent downloads
* CouchPotato - Movie download management
* SiCKRAGE - TV download management
* Logstash - Collect logs from pfSense

## Honeypot

This contains a docker-compose config for the Raspberry Pi Cowrie SSH honeypot.

[Link](./honeypot)

## TODO

* MySQL backup cronjob
