# Monitoring
System monitoring done with ELK stack and Prometheus/Grafana. All created as single docker-compose file with dependencies.

### System overview

### Setting up
Before starting up add `"127.0.0.1" monitoring.com"` to /etc/hosts, also
make sure that `grafana/grafana.db` has `472:472` ownership.
After it, run `docker-compose up -d`
It may take some time, because of healthcheck of kibana service. Kibana has to start before filebeat and metricbeat to make it possible for them to load dashboards.
Check running services with `docker-compose ps`, and logs with `docker-compose logs <service name>`

URLS with dashboards
* https://monitoring.com/grafana/dashboards
    * Docker monitoring with Prometheus and cAdvisor
    * Nginx monitoring with Elastic Filebeat
* https://monitoring.com/kibana/app/kibana#/dashboards
    * [Filebeat Nginx] Access and error logs ECS - Dashboard for the Filebeat Nginx module
    * [Filebeat Nginx] Overview ECS - Dashboard for the Filebeat Nginx module
    * [Metricbeat Nginx] Overview ECS - Overview dashboard for the Nginx module in Metricbeat

