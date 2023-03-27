# isaac-app

![Version: 1.3.2](https://img.shields.io/badge/Version-1.3.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | isaac-app-fe(nginx) | 13.2.18 |
| https://charts.bitnami.com/bitnami | isaac-cdn(nginx) | 13.2.18 |
| https://charts.bitnami.com/bitnami | isaac-app-renderer(nginx) | 13.2.18 |
| https://charts.bitnami.com/bitnami | isaac-content-editor(nginx) | 13.2.18 |
| https://charts.bitnami.com/bitnami | isaac-code-editor(nginx) | 13.2.18 |
| https://helm.elastic.co | elastic-search(elasticsearch) | 7.17.3 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| api.affinity | object | `{}` |  |
| api.autoscaling.enabled | bool | `false` |  |
| api.autoscaling.maxReplicas | int | `10` |  |
| api.autoscaling.minReplicas | int | `1` |  |
| api.autoscaling.scaleDown.stabilizationWindowSeconds | int | `300` |  |
| api.autoscaling.scaleUp.stabilizationWindowSeconds | int | `0` |  |
| api.autoscaling.targetCPU | int | `100` |  |
| api.autoscaling.targetMemory | int | `75` |  |
| api.config.contentKeySecretName | string | `""` |  |
| api.config.secretName | string | `""` |  |
| api.deployment.annotations | object | `{}` |  |
| api.gitSync.resources | object | `{}` |  |
| api.image.pullPolicy | string | `"IfNotPresent"` |  |
| api.image.repository | string | `"ghcr.io/isaaccomputerscience/isaac-api"` |  |
| api.image.tag | string | `"v1.0.0"` |  |
| api.imagePullSecrets | list | `[]` |  |
| api.ingress.annotations."nginx.ingress.kubernetes.io/proxy-cookie-path" | string | `"/isaac-api /"` |  |
| api.ingress.annotations."nginx.ingress.kubernetes.io/rewrite-target" | string | `"/isaac-api/$2"` |  |
| api.ingress.className | string | `"nginx"` |  |
| api.ingress.enabled | bool | `false` |  |
| api.ingress.hosts | list | `[]` |  |
| api.ingress.tls | list | `[]` |  |
| api.javaOptions | string | `"-Xmx2g"` |  |
| api.name | string | `"api"` |  |
| api.nodeSelector | object | `{}` |  |
| api.prometheusExport.enabled | bool | `false` |  |
| api.prometheusExport.path | string | `"/"` |  |
| api.prometheusExport.port | int | `9966` |  |
| api.resources | object | `{}` |  |
| api.service.port | int | `80` |  |
| api.service.type | string | `"ClusterIP"` |  |
| api.tolerations | list | `[]` |  |
| chemChecker.affinity | object | `{}` |  |
| chemChecker.image.pullPolicy | string | `"IfNotPresent"` |  |
| chemChecker.image.repository | string | `"ucamcldtg/chemistry-checker"` |  |
| chemChecker.image.tag | string | `"latest"` |  |
| chemChecker.imagePullSecrets | list | `[]` |  |
| chemChecker.ingress.enabled | bool | `false` |  |
| chemChecker.name | string | `"chemistry-checker"` |  |
| chemChecker.nodeSelector | object | `{}` |  |
| chemChecker.podAnnotations | object | `{}` |  |
| chemChecker.podSecurityContext | object | `{}` |  |
| chemChecker.replicaCount | int | `1` |  |
| chemChecker.resources | object | `{}` |  |
| chemChecker.securityContext | object | `{}` |  |
| chemChecker.service.port | int | `80` |  |
| chemChecker.service.type | string | `"ClusterIP"` |  |
| chemChecker.tolerations | list | `[]` |  |
| contentRepo.depth | int | `1000` |  |
| contentRepo.liveSha | string | `"fbb01c97c3210f77b4420ed043ebbac80f7200d3"` |  |
| contentRepo.taskPeriodSeconds | int | `60` |  |
| contentRepo.url | string | `"git@github.com:isaaccomputerscience/isaac-content.git"` |  |
| contentRepo.wait | int | `60` |  |
| editorAuth.affinity | object | `{}` |  |
| editorAuth.config | object | `{}` |  |
| editorAuth.deployment.annotations | object | `{}` |  |
| editorAuth.image.pullPolicy | string | `"IfNotPresent"` |  |
| editorAuth.image.repository | string | `"ghcr.io/isaaccomputerscience/isaac-editor-auth"` |  |
| editorAuth.image.tag | string | `"v1.0.0"` |  |
| editorAuth.imagePullSecrets | list | `[]` |  |
| editorAuth.ingress.annotations | object | `{}` |  |
| editorAuth.ingress.className | string | `"nginx"` |  |
| editorAuth.ingress.enabled | bool | `false` |  |
| editorAuth.ingress.hosts | list | `[]` |  |
| editorAuth.ingress.tls | list | `[]` |  |
| editorAuth.name | string | `"editor-auth"` |  |
| editorAuth.nodeSelector | object | `{}` |  |
| editorAuth.replicaCount | int | `1` |  |
| editorAuth.resources | object | `{}` |  |
| editorAuth.service.port | int | `80` |  |
| editorAuth.service.type | string | `"ClusterIP"` |  |
| editorAuth.tolerations | list | `[]` |  |
| elastic-search.clusterName | string | `"isaac-cs-content"` |  |
| elastic-search.createCert | bool | `false` |  |
| elastic-search.esConfig."elasticsearch.yml" | string | `"xpack.security.enabled: false\nxpack.security.transport.ssl.enabled: false\ningest.geoip.downloader.enabled: false\n"` |  |
| elastic-search.imageTag | string | `"7.17.6"` |  |
| elastic-search.persistence.enabled | bool | `false` |  |
| elastic-search.protocol | string | `"http"` |  |
| elastic-search.replicas | int | `1` |  |
| elastic-search.resources | object | `{}` |  |
| eqChecker.affinity | object | `{}` |  |
| eqChecker.image.pullPolicy | string | `"IfNotPresent"` |  |
| eqChecker.image.repository | string | `"ucamcldtg/equality-checker"` |  |
| eqChecker.image.tag | string | `"v0.13.0"` |  |
| eqChecker.imagePullSecrets | list | `[]` |  |
| eqChecker.name | string | `"equality-checker"` |  |
| eqChecker.nodeSelector | object | `{}` |  |
| eqChecker.podAnnotations | object | `{}` |  |
| eqChecker.podSecurityContext | object | `{}` |  |
| eqChecker.replicaCount | int | `1` |  |
| eqChecker.resources | object | `{}` |  |
| eqChecker.securityContext | object | `{}` |  |
| eqChecker.service.port | int | `80` |  |
| eqChecker.service.type | string | `"ClusterIP"` |  |
| eqChecker.tolerations | list | `[]` |  |
| etl.affinity | object | `{}` |  |
| etl.config.contentKeySecretName | string | `""` |  |
| etl.config.secretName | string | `""` |  |
| etl.deployment.annotations | object | `{}` |  |
| etl.gitSync.resources | object | `{}` |  |
| etl.image.pullPolicy | string | `"IfNotPresent"` |  |
| etl.image.repository | string | `"ghcr.io/isaaccomputerscience/isaac-api-etl"` |  |
| etl.image.tag | string | `"v1.0.0"` |  |
| etl.imagePullSecrets | list | `[]` |  |
| etl.ingress.enabled | bool | `false` |  |
| etl.javaOptions | string | `"-Xmx2g"` |  |
| etl.name | string | `"etl"` |  |
| etl.nodeSelector | object | `{}` |  |
| etl.replicaCount | int | `1` |  |
| etl.resources | object | `{}` |  |
| etl.service.port | int | `80` |  |
| etl.service.type | string | `"ClusterIP"` |  |
| etl.tolerations | list | `[]` |  |
| fullnameOverride | string | `""` |  |
| isaac-app-fe.autoscaling.enabled | bool | `false` |  |
| isaac-app-fe.autoscaling.maxReplicas | int | `10` |  |
| isaac-app-fe.autoscaling.minReplicas | int | `1` |  |
| isaac-app-fe.autoscaling.targetCPU | int | `100` |  |
| isaac-app-fe.autoscaling.targetMemory | int | `75` |  |
| isaac-app-fe.containerPorts.http | int | `80` |  |
| isaac-app-fe.image.registry | string | `"ghcr.io"` |  |
| isaac-app-fe.image.repository | string | `"isaaccomputerscience/isaac-react-app-cs"` |  |
| isaac-app-fe.image.tag | string | `"v1.0.0"` |  |
| isaac-app-fe.ingress.annotations | object | `{}` |  |
| isaac-app-fe.ingress.enabled | bool | `false` |  |
| isaac-app-fe.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-app-fe.ingress.path | string | `"/"` |  |
| isaac-app-fe.resources | object | `{}` |  |
| isaac-app-fe.service.type | string | `"ClusterIP"` |  |
| isaac-app-renderer.containerPorts.http | int | `80` |  |
| isaac-app-renderer.image.registry | string | `"ghcr.io"` |  |
| isaac-app-renderer.image.repository | string | `"isaaccomputerscience/isaac-react-app-cs-renderer"` |  |
| isaac-app-renderer.image.tag | string | `"v1.0.0"` |  |
| isaac-app-renderer.ingress.annotations | object | `{}` |  |
| isaac-app-renderer.ingress.enabled | bool | `false` |  |
| isaac-app-renderer.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-app-renderer.ingress.path | string | `"/"` |  |
| isaac-app-renderer.resources | object | `{}` |  |
| isaac-app-renderer.service.type | string | `"ClusterIP"` |  |
| isaac-cdn.containerPorts.http | int | `80` |  |
| isaac-cdn.image.registry | string | `"ghcr.io"` |  |
| isaac-cdn.image.repository | string | `"isaaccomputerscience/isaac-cdn"` |  |
| isaac-cdn.image.tag | string | `"v1.0.0"` |  |
| isaac-cdn.ingress.annotations | object | `{}` |  |
| isaac-cdn.ingress.enabled | bool | `false` |  |
| isaac-cdn.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-cdn.ingress.path | string | `"/"` |  |
| isaac-cdn.resources | object | `{}` |  |
| isaac-cdn.service.type | string | `"ClusterIP"` |  |
| isaac-code-editor.containerPorts.http | int | `80` |  |
| isaac-code-editor.image.registry | string | `"ghcr.io"` |  |
| isaac-code-editor.image.repository | string | `"isaaccomputerscience/isaac-code-editor"` |  |
| isaac-code-editor.image.tag | string | `"v1.0.0"` |  |
| isaac-code-editor.ingress.annotations | object | `{}` |  |
| isaac-code-editor.ingress.enabled | bool | `false` |  |
| isaac-code-editor.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-code-editor.ingress.path | string | `"/"` |  |
| isaac-code-editor.resources | object | `{}` |  |
| isaac-code-editor.service.type | string | `"ClusterIP"` |  |
| isaac-content-editor.containerPorts.http | int | `80` |  |
| isaac-content-editor.image.registry | string | `"ghcr.io"` |  |
| isaac-content-editor.image.repository | string | `"isaaccomputerscience/isaac-content-editor"` |  |
| isaac-content-editor.image.tag | string | `"v1.0.0"` |  |
| isaac-content-editor.ingress.annotations | object | `{}` |  |
| isaac-content-editor.ingress.enabled | bool | `false` |  |
| isaac-content-editor.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-content-editor.ingress.path | string | `"/"` |  |
| isaac-content-editor.resources | object | `{}` |  |
| isaac-content-editor.service.type | string | `"ClusterIP"` |  |
| nameOverride | string | `""` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
