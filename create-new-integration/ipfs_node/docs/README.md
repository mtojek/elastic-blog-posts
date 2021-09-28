# IPFS Node

This is a new integration created using the [elastic-package](https://github.com/elastic/elastic-package) tool.

## Application logs

An example event for `application` looks as following:

```json
{
    "@timestamp": "2021-09-28T12:33:32.651Z",
    "agent": {
        "ephemeral_id": "ed140b5f-c62a-416f-a23d-5ff2e1a4274d",
        "hostname": "docker-fleet-agent",
        "id": "61f74704-8f2c-47a9-853a-c4407b71f3cc",
        "name": "docker-fleet-agent",
        "type": "filebeat",
        "version": "7.15.0"
    },
    "data_stream": {
        "dataset": "ipfs_node.application",
        "namespace": "ep",
        "type": "logs"
    },
    "ecs": {
        "version": "1.11.0"
    },
    "elastic_agent": {
        "id": "61f74704-8f2c-47a9-853a-c4407b71f3cc",
        "snapshot": true,
        "version": "7.15.0"
    },
    "event": {
        "agent_id_status": "verified",
        "dataset": "ipfs_node.application",
        "ingested": "2021-09-28T12:33:36Z",
        "timezone": "+00:00"
    },
    "host": {
        "architecture": "x86_64",
        "containerized": true,
        "hostname": "docker-fleet-agent",
        "id": "6505f7ca36739e7eb909bdb52bf3ec18",
        "ip": [
            "192.168.128.7"
        ],
        "mac": [
            "02:42:c0:a8:80:07"
        ],
        "name": "docker-fleet-agent",
        "os": {
            "codename": "Core",
            "family": "redhat",
            "kernel": "5.10.25-linuxkit",
            "name": "CentOS Linux",
            "platform": "centos",
            "type": "linux",
            "version": "7 (Core)"
        }
    },
    "input": {
        "type": "log"
    },
    "log": {
        "file": {
            "path": "/tmp/service_logs/ipfs-node-0.log"
        },
        "offset": 0
    },
    "message": "Changing user to ipfs"
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| ecs.version | ECS version this event conforms to. `ecs.version` is a required field and must exist in all events. When querying across multiple indices -- which may conform to slightly different ECS versions -- this field lets integrations adjust to the schema version of the events. | keyword |
| input.type | Input type | keyword |
| log.file.path | Full path to the log file this event came from, including the file name. It should include the drive letter, when appropriate. If the event wasn't read from a log file, do not populate this field. | keyword |
| log.offset | Logfile offset | long |
| message | For log events the message field contains the log message, optimized for viewing in a log viewer. For structured logs without an original message field, other fields can be concatenated to form a human-readable summary of the event. If multiple messages exist, they can be combined into one message. | text |


## Repository metrics

An example event for `repository` looks as following:

```json
{
    "@timestamp": "2021-09-28T12:34:22.104Z",
    "agent": {
        "ephemeral_id": "e8f271a2-94b3-4603-814c-c325b769f722",
        "hostname": "docker-fleet-agent",
        "id": "61f74704-8f2c-47a9-853a-c4407b71f3cc",
        "name": "docker-fleet-agent",
        "type": "metricbeat",
        "version": "7.15.0"
    },
    "data_stream": {
        "dataset": "ipfs_node.repository",
        "namespace": "ep",
        "type": "metrics"
    },
    "ecs": {
        "version": "1.11.0"
    },
    "elastic_agent": {
        "id": "61f74704-8f2c-47a9-853a-c4407b71f3cc",
        "snapshot": true,
        "version": "7.15.0"
    },
    "event": {
        "agent_id_status": "verified",
        "dataset": "ipfs_node.repository",
        "duration": 5698900,
        "ingested": "2021-09-28T12:34:25Z",
        "module": "http"
    },
    "host": {
        "architecture": "x86_64",
        "containerized": true,
        "hostname": "docker-fleet-agent",
        "id": "6505f7ca36739e7eb909bdb52bf3ec18",
        "ip": [
            "192.168.128.7"
        ],
        "mac": [
            "02:42:c0:a8:80:07"
        ],
        "name": "docker-fleet-agent",
        "os": {
            "codename": "Core",
            "family": "redhat",
            "kernel": "5.10.25-linuxkit",
            "name": "CentOS Linux",
            "platform": "centos",
            "type": "linux",
            "version": "7 (Core)"
        }
    },
    "http": {
        "repository": {
            "NumObjects": 22,
            "RepoPath": "/data/ipfs",
            "RepoSize": 118313,
            "StorageMax": 10000000000,
            "Version": "fs-repo@11"
        }
    },
    "metricset": {
        "name": "json",
        "period": 10000
    },
    "service": {
        "address": "http://elastic-package-service_ipfs_node_1:5001/api/v0/repo/stat",
        "type": "http"
    }
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| ecs.version | ECS version this event conforms to. `ecs.version` is a required field and must exist in all events. When querying across multiple indices -- which may conform to slightly different ECS versions -- this field lets integrations adjust to the schema version of the events. | keyword |
| error.message | Error message. | text |
| http.repository.NumObjects | Number of objects in the repository | long |
| http.repository.RepoPath | Path to the repository | keyword |
| http.repository.RepoSize | Size of the repository | long |
| http.repository.StorageMax | Max size of the storage | long |
| http.repository.Version | Storage version | keyword |
| service.address | Service address | keyword |
| service.type | The type of the service data is collected from. The type can be used to group and correlate logs and metrics from one service type. Example: If logs or metrics are collected from Elasticsearch, `service.type` would be `elasticsearch`. | keyword |


## Traffic metrics

An example event for `traffic` looks as following:

```json
{
    "@timestamp": "2021-09-28T12:35:10.859Z",
    "agent": {
        "ephemeral_id": "3828d707-7ef6-4af9-9b84-28cdbf8f22cf",
        "hostname": "docker-fleet-agent",
        "id": "61f74704-8f2c-47a9-853a-c4407b71f3cc",
        "name": "docker-fleet-agent",
        "type": "metricbeat",
        "version": "7.15.0"
    },
    "data_stream": {
        "dataset": "ipfs_node.traffic",
        "namespace": "ep",
        "type": "metrics"
    },
    "ecs": {
        "version": "1.11.0"
    },
    "elastic_agent": {
        "id": "61f74704-8f2c-47a9-853a-c4407b71f3cc",
        "snapshot": true,
        "version": "7.15.0"
    },
    "event": {
        "agent_id_status": "verified",
        "dataset": "ipfs_node.traffic",
        "duration": 3218100,
        "ingested": "2021-09-28T12:35:14Z",
        "module": "http"
    },
    "host": {
        "architecture": "x86_64",
        "containerized": true,
        "hostname": "docker-fleet-agent",
        "id": "6505f7ca36739e7eb909bdb52bf3ec18",
        "ip": [
            "192.168.128.7"
        ],
        "mac": [
            "02:42:c0:a8:80:07"
        ],
        "name": "docker-fleet-agent",
        "os": {
            "codename": "Core",
            "family": "redhat",
            "kernel": "5.10.25-linuxkit",
            "name": "CentOS Linux",
            "platform": "centos",
            "type": "linux",
            "version": "7 (Core)"
        }
    },
    "http": {
        "traffic": {
            "RateIn": 6143.101688596616,
            "RateOut": 2978.29294020491,
            "TotalIn": 160014,
            "TotalOut": 55738
        }
    },
    "metricset": {
        "name": "json",
        "period": 10000
    },
    "service": {
        "address": "http://elastic-package-service_ipfs_node_1:5001/api/v0/stats/bw",
        "type": "http"
    }
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| ecs.version | ECS version this event conforms to. `ecs.version` is a required field and must exist in all events. When querying across multiple indices -- which may conform to slightly different ECS versions -- this field lets integrations adjust to the schema version of the events. | keyword |
| error.message | Error message. | text |
| http.traffic.RateIn | In network rate | scaled_float |
| http.traffic.RateOut | On network rate | scaled_float |
| http.traffic.TotalIn | Total in traffic | long |
| http.traffic.TotalOut | Total out traffic | long |
| service.address | Service address | keyword |
| service.type | The type of the service data is collected from. The type can be used to group and correlate logs and metrics from one service type. Example: If logs or metrics are collected from Elasticsearch, `service.type` would be `elasticsearch`. | keyword |
