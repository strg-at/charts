# behave-crawler

![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.4.4](https://img.shields.io/badge/AppVersion-1.4.4-informational?style=flat-square)

STRG.BeHave crawler

**Homepage:** <https://github.com/strg-at/charts/tree/main/charts/behave-crawler>

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
| controller.replicas | int | `1` | Number of desired pods. Only one instance needed. |
| env.APP | string | `"crawler"` | The app usage (crawler or blacklist) |
| env.BEHAVE_CLIENT_ID | string | `"strg"` | beHave client id used as logging reference aswel as for NATS message routing |
| env.CRAWL_INTERVAL | string | `""` | The crawl interval in days |
| env.NATS_PASS | string | `""` | The nats password |
| env.NATS_SERVER | string | `""` | The nats server address |
| env.NATS_USER | string | `""` | The nats user |
| env.NODE_ENV | string | `"production"` | The default node environment |
| env.NODE_LOG_LEVEL | string | `"info"` | The node log level |
| env.PGDATABASE | string | `""` | The postgres database name |
| env.PGHOST | string | `""` | The postgres host ip or FQDN |
| env.PGMAXCON | string | `"1"` | The postgres number of connections |
| env.PGPASSWORD | string | `""` | The postgres password |
| env.PGPORT | string | `"5432"` | The postgres port to connect default to 5432 |
| env.PGUSER | string | `""` | The postgres user |
| env.PORT | string | `"3000"` | The node application port |
| env.TZ | string | `"UTC"` | The timezone in the container |
| image.repository | string | `"eu.gcr.io/logical-sled-220910/strg/behave/crawler"` | image repository |
| image.tag | string | `""` | image tag |
| jobs.createDB.PGADMINPASS | string | `""` | The postgres admin password to setup the database - must be set! |
| jobs.createDB.PGADMINUSER | string | `""` | The postgres admin user to setup the database - must be set! |
| probes.liveness.enabled | bool | `false` |  |
| probes.readiness.enabled | bool | `false` |  |
| probes.startup.enabled | bool | `false` |  |
| securityContext.allowPrivilegeEscalation | bool | `false` | do not allow privilege escalation for security reasons |
| securityContext.capabilities.drop[0] | string | `"ALL"` | drop all privileges as we dont need them |
| securityContext.readOnlyRootFilesystem | bool | `true` | set root fs to read only for security reasons |
| securityContext.runAsNonRoot | bool | `true` | do not run as root for security reasons |
| securityContext.runAsUser | int | `1000` | run as user with <id> |
| service.main.enabled | bool | `false` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
