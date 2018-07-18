# filebeat

filebeat.inputs:
- type: log
  enabled: true
  paths:
    - /var/log/*.log
document_type: syslog
output.logstash:
  hosts: ["35.237.40.92:5443"]
  bulk_max_size: 1024
  ssl.certificate_authorities: ["/etc/pki/tls/certs/logstash-forwarder.crt"]
  template.name: "filebeat"
  template.path: "filebeat.template.json"
  template.overwrite: false

