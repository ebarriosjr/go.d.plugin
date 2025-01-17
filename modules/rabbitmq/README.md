# rabbitmq

Module monitors [`RabbitMQ`](https://www.rabbitmq.com/) performance and health metrics.

It collects data using following endpoints:
  - `/api/overview`
  - `/api/node/{node_name}`
  - `/api/vhosts`

#### charts

It produces the following charts:
  - Queued Messages in `messages`
  - Messages in `messages/s`
  - Global Counts in `counts`
  - File Descriptors in `descriptors`
  - Socket Descriptors in `descriptors`
  - Erlang Processes in `processes`
  - Erlang run queue in `processes`
  - Memory in `MiB`
  - Disk Space in `GiB`

Per vhost charts:
  - Messages in `messages/s`

#### configuration

```yaml
jobs:
  - name: local
    url : http://localhost:15672
      
  - name: remote
    url : http://203.0.113.10:15672

```
For all available options please see module [configuration file](https://github.com/netdata/go.d.plugin/blob/master/config/go.d/rabbitmq.conf).

When no configuration file is found, module tries to connect to: `localhost:15672`.

---
