# behave-tracking-service

![Version: 0.2.1](https://img.shields.io/badge/Version-0.2.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 5.0.12](https://img.shields.io/badge/AppVersion-5.0.12-informational?style=flat-square)

STRG.BeHave tracking-service

**Homepage:** <https://github.com/strg-at/charts/tree/main/charts/behave-tracking-service>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Nils Müller | <nils.mueller@strg.at> |  |
| Jasmin Müller | <jasmin.mueller@strg.at> |  |

## Requirements

Kubernetes: `>=1.16.0-0`

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controller.replicas | int | `3` | Number of desired pods. We use 3 minimum to assure no outage durring rollout/preemtible node restarts |
| env.BEHAVE_CLIENT_ID | string | `"strg"` | beHave client id used in logging reference aswel as in NATS message routing |
| env.CONNECTION_TIMEOUT | string | `"60000"` | beHave websocket connection timeout |
| env.KEEPALIVE_TIMEOUT | string | `"30000"` | beHave keep alive timeout |
| env.NATS_PASS | string | `""` | the nats password |
| env.NATS_SERVER | string | `""` | the nats server address |
| env.NATS_USER | string | `""` | the nats user |
| env.NODE_ENV | string | `"production"` | The default nodejs environment |
| env.PAYLOAD_MAX_LENGTH | string | `"10000"` | the maximum length of bytes before droping websocket frames |
| env.PGDATABASE | string | `""` | The postgres database name |
| env.PGHOST | string | `""` | The postgres host ip or FQDN |
| env.PGMAXCON | string | `"5"` | The postgres number of connections |
| env.PGPASSWORD | string | `""` | The postgres password |
| env.PGPORT | string | `"5432"` | The postgres port to connect default to 5432 |
| env.PGUSER | string | `""` | The postgres user |
| env.PORT | string | `"3000"` | websocket listening port |
| env.STORE_RAW_EVENTS | string | `"false"` | store raw events in db (require a working db connection) |
| env.TZ | string | `"UTC"` | The timezone in the container |
| image.repository | string | `"eu.gcr.io/logical-sled-220910/strg/behave/tracking-service"` | image repository |
| image.tag | string | `""` | image tag |
| probes | object | See below | [[ref]](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) |
| probes.liveness | object | See below | Liveness probe configuration |
| probes.liveness.enabled | bool | `false` | Enable the liveness probe |
| probes.readiness | object | See below | Redainess probe configuration |
| probes.readiness.enabled | bool | `false` | Enable the readiness probe |
| probes.startup | object | See below | Startup probe configuration |
| probes.startup.enabled | bool | `false` | Enable the startup probe |
| securityContext.allowPrivilegeEscalation | bool | `false` | do not allow privilege escalation for security reasons |
| securityContext.capabilities.drop[0] | string | `"ALL"` | drop all privileges as we dont need them |
| securityContext.readOnlyRootFilesystem | bool | `true` | set root fs to read only for security reasons |
| securityContext.runAsNonRoot | bool | `true` | do not run as root for security reasons |
| securityContext.runAsUser | int | `1000` | run as user with <id> |
| service | object | See below | Configure the services for the chart here. Additional services can be added by adding a dictionary key similar to the 'main' service. |
| service.main.ports | object | See below | Configure the Service port information here. Additional ports can be added by adding a dictionary key similar to the 'http' service. |
| service.main.ports.http.port | int | `3000` | The port number |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
