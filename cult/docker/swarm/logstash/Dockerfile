FROM ind3x/rpi-logstash

RUN logstash-plugin install logstash-output-influxdb

CMD ["-f", "/etc/logstash"]
