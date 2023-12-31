# backblaze-operator

![Version: 0.1.2](https://img.shields.io/badge/Version-0.1.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

A Kubernetes Operator for Backblaze B2 object storage

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controllerManager.kubeRbacProxy.args[0] | string | `"--secure-listen-address=0.0.0.0:8443"` |  |
| controllerManager.kubeRbacProxy.args[1] | string | `"--upstream=http://127.0.0.1:8080/"` |  |
| controllerManager.kubeRbacProxy.args[2] | string | `"--logtostderr=true"` |  |
| controllerManager.kubeRbacProxy.args[3] | string | `"--v=0"` |  |
| controllerManager.kubeRbacProxy.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| controllerManager.kubeRbacProxy.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| controllerManager.kubeRbacProxy.image.repository | string | `"gcr.io/kubebuilder/kube-rbac-proxy"` |  |
| controllerManager.kubeRbacProxy.image.tag | string | `"v0.13.1"` |  |
| controllerManager.kubeRbacProxy.resources | object | `{"limits":{"cpu":"500m","memory":"128Mi"},"requests":{"cpu":"5m","memory":"64Mi"}}` | Define resources requests and limits for RBAC proxy |
| controllerManager.manager.args[0] | string | `"--health-probe-bind-address=:8081"` |  |
| controllerManager.manager.args[1] | string | `"--metrics-bind-address=127.0.0.1:8080"` |  |
| controllerManager.manager.args[2] | string | `"--leader-elect"` |  |
| controllerManager.manager.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| controllerManager.manager.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| controllerManager.manager.image.repository | string | `"ghcr.io/ihyoudou/backblaze-operator"` |  |
| controllerManager.manager.image.tag | string | `"latest"` |  |
| controllerManager.manager.resources | object | `{"limits":{"cpu":"500m","memory":"128Mi"},"requests":{"cpu":"10m","memory":"64Mi"}}` | Define resources requests and limits for backblaze-operator |
| controllerManager.replicas | int | `1` |  |
| controllerManager.serviceAccount.annotations | object | `{}` |  |
| credentials | object | `{"b2ApplicationId":"","b2ApplicationKey":"","b2Region":"","secret":{"name":"","useSecret":false}}` | Credentials for Backblaze B2 Master Application Key |
| credentials.b2ApplicationId | string | `""` | Backblaze B2 Master Application Key ID |
| credentials.b2ApplicationKey | string | `""` | Backblaze B2 Master Application Key Key |
| credentials.b2Region | string | `""` | Backblaze B2 Region of account |
| credentials.secret | object | `{"name":"","useSecret":false}` | Use Backblaze B2 credentials from existing secret |
| credentials.secret.name | string | `""` | Name of secret with B2 credentials |
| credentials.secret.useSecret | bool | `false` | Use existing secret instead of providing credentials in values (true/false) |
| kubernetesClusterDomain | string | `"cluster.local"` |  |
| metricsService.ports[0].name | string | `"https"` |  |
| metricsService.ports[0].port | int | `8443` |  |
| metricsService.ports[0].protocol | string | `"TCP"` |  |
| metricsService.ports[0].targetPort | string | `"https"` |  |
| metricsService.type | string | `"ClusterIP"` |  |

