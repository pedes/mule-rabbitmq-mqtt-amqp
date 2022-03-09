# mule-rabbitmq-mqtt-amqp
Example how to send/publish messages using MQTT and AMQP protocols with RabbitMQ Broker

## Get Started - How to Run

1. Install RabbitMQ (https://www.rabbitmq.com/download.html)
2. Run your RabbitMQ Server (cd /usr/local/opt/rabbitmq/sbin && ./rabbitmq-server start )

```
./rabbitmq-server start                 
2022-03-08 21:36:44.672216+01:00 [info] <0.227.0> Feature flags: list of feature flags found:
2022-03-08 21:36:44.683956+01:00 [info] <0.227.0> Feature flags:   [x] implicit_default_bindings
2022-03-08 21:36:44.683990+01:00 [info] <0.227.0> Feature flags:   [x] maintenance_mode_status
2022-03-08 21:36:44.684004+01:00 [info] <0.227.0> Feature flags:   [x] quorum_queue
2022-03-08 21:36:44.684018+01:00 [info] <0.227.0> Feature flags:   [x] stream_queue
2022-03-08 21:36:44.684033+01:00 [info] <0.227.0> Feature flags:   [x] user_limits
2022-03-08 21:36:44.684046+01:00 [info] <0.227.0> Feature flags:   [x] virtual_host_metadata
2022-03-08 21:36:44.684056+01:00 [info] <0.227.0> Feature flags: feature flag states written to disk: yes
2022-03-08 21:36:45.069230+01:00 [noti] <0.44.0> Application syslog exited with reason: stopped
2022-03-08 21:36:45.069273+01:00 [noti] <0.227.0> Logging: switching to configured handler(s); following messages may not be visible in this log output

  ##  ##      RabbitMQ 3.9.13
  ##  ##
  ##########  Copyright (c) 2007-2022 VMware, Inc. or its affiliates.
  ######  ##
  ##########  Licensed under the MPL 2.0. Website: https://rabbitmq.com

  Erlang:      24.2.2 [jit]
  TLS Library: OpenSSL - OpenSSL 1.1.1m  14 Dec 2021

  Doc guides:  https://rabbitmq.com/documentation.html
  Support:     https://rabbitmq.com/contact.html
  Tutorials:   https://rabbitmq.com/getstarted.html
  Monitoring:  https://rabbitmq.com/monitoring.html

  Logs: /usr/local/var/log/rabbitmq/rabbit@localhost.log
        /usr/local/var/log/rabbitmq/rabbit@localhost_upgrade.log
        <stdout>

  Config file(s): (none)

  Starting broker... completed with 7 plugins.
```
  
3. Enable the MQTT plugin on Rabbit
```
./rabbitmqctl add_user mqtt-test mqtt-test
Adding user "mqtt-test" ...
Done. Don't forget to grant the user permissions to some virtual hosts! See 'rabbitmqctl help set_permissions' to learn more.

./rabbitmqctl set_permissions -p / mqtt-test ".*" ".*" ".*"
Setting permissions for user "mqtt-test" in vhost "/" ...

./rabbitmqctl set_user_tags mqtt-test management
Setting tags for user "mqtt-test" to [management] ...
```

4. Import this project in anypoint studio and run it (it works with the default configuration, guest user, port 1883)
5. This project has configuration for both protocols, AMQP and MQTT, each case has a different HTTP listener/endpoint to be tested.

### References
- https://docs.mulesoft.com/mqtt3-connector/1.0/mqtt3-connector-listener
- https://www.rabbitmq.com/mqtt.html#enabling-plugin
- https://www.goformule.com/2020/04/mule-4-rabbitmq-integration-with-mule-4.html
