# isaac-app

![Version: 1.1.11](https://img.shields.io/badge/Version-1.1.11-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for Isaac Computer Science

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
| api.config.secretName | string | `"isaac-secrets"` |  |
| api.config.sshSecretName | string | `"isaac-ssh-key"` |  |
| api.deployment.annotations."configmap.reloader.stakater.com/reload" | string | `"isaac-app-content-indices"` |  |
| api.deployment.annotations."secret.reloader.stakater.com/reload" | string | `"isaac-secrets,isaac-ssh-key"` |  |
| api.gitSync.resources | object | `{}` |  |
| api.image.pullPolicy | string | `"IfNotPresent"` |  |
| api.image.repository | string | `"ghcr.io/isaaccomputerscience/isaac-api"` |  |
| api.image.tag | string | `"v1.0.0"` |  |
| api.imagePullSecrets | list | `[]` |  |
| api.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| api.ingress.annotations."nginx.ingress.kubernetes.io/proxy-cookie-path" | string | `"/isaac-api /"` |  |
| api.ingress.annotations."nginx.ingress.kubernetes.io/rewrite-target" | string | `"/isaac-api/$2"` |  |
| api.ingress.className | string | `"nginx"` |  |
| api.ingress.enabled | string | `"enabled"` |  |
| api.ingress.hosts[0].host | string | `"www.non-prod.isaaccomputerscience.org"` |  |
| api.ingress.hosts[0].paths[0].path | string | `"/api/([^/]+)/(.*)$"` |  |
| api.ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| api.ingress.tls[0].hosts[0] | string | `"www.non-prod.isaaccomputerscience.org"` |  |
| api.ingress.tls[0].secretName | string | `"www-isaac"` |  |
| api.name | string | `"api"` |  |
| api.nodeSelector | object | `{}` |  |
| api.prometheusExport.enabled | bool | `true` |  |
| api.prometheusExport.path | string | `"/"` |  |
| api.prometheusExport.port | int | `9966` |  |
| api.replicaCount | int | `1` |  |
| api.resources | object | `{}` |  |
| api.service.port | int | `80` |  |
| api.service.type | string | `"ClusterIP"` |  |
| api.tolerations | list | `[]` |  |
| chemChecker.affinity | object | `{}` |  |
| chemChecker.image.pullPolicy | string | `"Always"` |  |
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
| contentRepo.latestSha | string | `"e1909b05d08fecd5b34984f52f38f6a75754c915"` |  |
| contentRepo.liveSha | string | `"542dc78f3d5cc3a5514f62bdc6093d9a772a2f72"` |  |
| contentRepo.url | string | `"git@github.com:isaaccomputerscience/rutherford-content.git"` |  |
| contentRepo.wait | int | `60` |  |
| editorAuth.affinity | object | `{}` |  |
| editorAuth.config.allowOriginHeader | string | `"https://content-editor.non-prod.isaaccomputerscience.org"` |  |
| editorAuth.config.secretName | string | `"isaac-editor-auth-secrets"` |  |
| editorAuth.deployment.annotations."secret.reloader.stakater.com/reload" | string | `"isaac-editor-auth-secrets"` |  |
| editorAuth.image.pullPolicy | string | `"IfNotPresent"` |  |
| editorAuth.image.repository | string | `"ghcr.io/isaaccomputerscience/isaac-editor-auth"` |  |
| editorAuth.image.tag | string | `"v1.0.0"` |  |
| editorAuth.imagePullSecrets | list | `[]` |  |
| editorAuth.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| editorAuth.ingress.className | string | `"nginx"` |  |
| editorAuth.ingress.enabled | string | `"enabled"` |  |
| editorAuth.ingress.hosts[0].host | string | `"editor-auth.non-prod.isaaccomputerscience.org"` |  |
| editorAuth.ingress.hosts[0].paths[0].path | string | `"/"` |  |
| editorAuth.ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| editorAuth.ingress.tls[0].hosts[0] | string | `"editor-auth.non-prod.isaaccomputerscience.org"` |  |
| editorAuth.ingress.tls[0].secretName | string | `"editor-auth-isaac"` |  |
| editorAuth.name | string | `"editor-auth"` |  |
| editorAuth.nodeSelector | object | `{}` |  |
| editorAuth.replicaCount | int | `1` |  |
| editorAuth.resources | object | `{}` |  |
| editorAuth.service.port | int | `80` |  |
| editorAuth.service.type | string | `"ClusterIP"` |  |
| editorAuth.tolerations | list | `[]` |  |
| elastic-search.clusterName | string | `"isaac-cs-content"` |  |
| elastic-search.createCert | bool | `false` |  |
| elastic-search.esConfig."elasticsearch.yml" | string | `"xpack.security.enabled: false\nxpack.security.transport.ssl.enabled: false\n"` |  |
| elastic-search.extraEnvs[0].name | string | `"ELASTIC_PASSWORD"` |  |
| elastic-search.extraEnvs[0].valueFrom.secretKeyRef.key | string | `"elasticsearch-pw"` |  |
| elastic-search.extraEnvs[0].valueFrom.secretKeyRef.name | string | `"isaac-secrets"` |  |
| elastic-search.imageTag | string | `"7.17.6"` |  |
| elastic-search.persistence.enabled | bool | `false` |  |
| elastic-search.protocol | string | `"http"` |  |
| elastic-search.replicas | int | `1` |  |
| elastic-search.resources | object | `{}` |  |
| eqChecker.affinity | object | `{}` |  |
| eqChecker.image.pullPolicy | string | `"Always"` |  |
| eqChecker.image.repository | string | `"ucamcldtg/equality-checker"` |  |
| eqChecker.image.tag | string | `"latest"` |  |
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
| etl.config.apiVersion | string | `"v3.3.2-snapshot"` |  |
| etl.config.secretName | string | `"isaac-secrets"` |  |
| etl.config.sshSecretName | string | `"isaac-ssh-key"` |  |
| etl.deployment.annotations."configmap.reloader.stakater.com/reload" | string | `"isaac-app-content-indices"` |  |
| etl.deployment.annotations."secret.reloader.stakater.com/reload" | string | `"isaac-secrets,isaac-ssh-key"` |  |
| etl.gitSync.resources | object | `{}` |  |
| etl.image.pullPolicy | string | `"IfNotPresent"` |  |
| etl.image.repository | string | `"ghcr.io/isaaccomputerscience/isaac-api-etl"` |  |
| etl.image.tag | string | `"v1.0.0"` |  |
| etl.imagePullSecrets | list | `[]` |  |
| etl.ingress.enabled | bool | `false` |  |
| etl.name | string | `"etl"` |  |
| etl.nodeSelector | object | `{}` |  |
| etl.replicaCount | int | `1` |  |
| etl.resources | object | `{}` |  |
| etl.service.port | int | `80` |  |
| etl.service.type | string | `"ClusterIP"` |  |
| etl.tolerations | list | `[]` |  |
| fullnameOverride | string | `""` |  |
| isaac-app-fe.containerPorts.http | int | `80` |  |
| isaac-app-fe.image.registry | string | `"ghcr.io"` |  |
| isaac-app-fe.image.repository | string | `"isaaccomputerscience/isaac-react-app-cs"` |  |
| isaac-app-fe.image.tag | string | `"v1.0.0"` |  |
| isaac-app-fe.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| isaac-app-fe.ingress.annotations."nginx.ingress.kubernetes.io/configuration-snippet" | string | `"more_set_headers \"Content-Security-Policy: default-src 'self' wss://www.non-prod.isaaccomputerscience.org https://cdn.non-prod.isaaccomputerscience.org https://www.google-analytics.com https://www.youtube-nocookie.com https://www.youtube.com; object-src 'none'; frame-src 'self' https://content-editor.non-prod.isaaccomputerscience.org  https://www.youtube-nocookie.com; img-src 'self' data: https://cdn.non-prod.isaaccomputerscience.org https://www.google-analytics.com https://*.tile.openstreetmap.org https://developers.google.com; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src 'self' https://cdn.www.non-prod.isaaccomputerscience.org https://fonts.gstatic.com;\";\n"` |  |
| isaac-app-fe.ingress.enabled | bool | `true` |  |
| isaac-app-fe.ingress.hostname | string | `"www.non-prod.isaaccomputerscience.org"` |  |
| isaac-app-fe.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-app-fe.ingress.path | string | `"/"` |  |
| isaac-app-fe.resources | object | `{}` |  |
| isaac-app-fe.service.type | string | `"ClusterIP"` |  |
| isaac-app-renderer.containerPorts.http | int | `80` |  |
| isaac-app-renderer.image.registry | string | `"ghcr.io"` |  |
| isaac-app-renderer.image.repository | string | `"isaaccomputerscience/isaac-react-app-cs-renderer"` |  |
| isaac-app-renderer.image.tag | string | `"v1.0.0"` |  |
| isaac-app-renderer.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| isaac-app-renderer.ingress.annotations."nginx.ingress.kubernetes.io/configuration-snippet" | string | `"more_set_headers \"default-src 'self' https://cdn.non-prod.isaaccomputerscience.org https://www.staging.non-prod.isaaccomputerscience.org https://www.youtube-nocookie.com https://www.youtube.com; object-src 'none'; frame-src 'self' https://content-editor.non-prod.isaaccomputerscience.org https://www.youtube-nocookie.com; img-src 'self' data: https://cdn.non-prod.isaaccomputerscience.org https://www.staging.non-prod.isaaccomputerscience.org https://*.tile.openstreetmap.org https://developers.google.com; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src 'self' https://cdn.non-prod.isaaccomputerscience.org https://fonts.gstatic.com; frame-ancestors 'self' https://content-editor.non-prod.isaaccomputerscience.org;\";\n"` |  |
| isaac-app-renderer.ingress.enabled | bool | `true` |  |
| isaac-app-renderer.ingress.extraTls[0].hosts[0] | string | `"editor-preview.non-prod.isaaccomputerscience.org"` |  |
| isaac-app-renderer.ingress.extraTls[0].secretName | string | `"editor-preview-isaac"` |  |
| isaac-app-renderer.ingress.hostname | string | `"editor-preview.non-prod.isaaccomputerscience.org"` |  |
| isaac-app-renderer.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-app-renderer.ingress.path | string | `"/"` |  |
| isaac-app-renderer.resources | object | `{}` |  |
| isaac-app-renderer.service.type | string | `"ClusterIP"` |  |
| isaac-cdn.containerPorts.http | int | `80` |  |
| isaac-cdn.image.registry | string | `"ghcr.io"` |  |
| isaac-cdn.image.repository | string | `"isaaccomputerscience/isaac-cdn"` |  |
| isaac-cdn.image.tag | string | `"v1.0.0"` |  |
| isaac-cdn.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| isaac-cdn.ingress.enabled | bool | `true` |  |
| isaac-cdn.ingress.extraTls[0].hosts[0] | string | `"cdn.non-prod.isaaccomputerscience.org"` |  |
| isaac-cdn.ingress.extraTls[0].secretName | string | `"cdn-isaac"` |  |
| isaac-cdn.ingress.hostname | string | `"cdn.non-prod.isaaccomputerscience.org"` |  |
| isaac-cdn.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-cdn.ingress.path | string | `"/"` |  |
| isaac-cdn.resources | object | `{}` |  |
| isaac-cdn.service.type | string | `"ClusterIP"` |  |
| isaac-code-editor.containerPorts.http | int | `80` |  |
| isaac-code-editor.image.registry | string | `"ghcr.io"` |  |
| isaac-code-editor.image.repository | string | `"isaaccomputerscience/isaac-code-editor"` |  |
| isaac-code-editor.image.tag | string | `"v1.0.0"` |  |
| isaac-code-editor.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| isaac-code-editor.ingress.enabled | bool | `true` |  |
| isaac-code-editor.ingress.extraTls[0].hosts[0] | string | `"code-editor.non-prod.isaaccomputerscience.org"` |  |
| isaac-code-editor.ingress.extraTls[0].secretName | string | `"code-editor-isaac"` |  |
| isaac-code-editor.ingress.hostname | string | `"code-editor.non-prod.isaaccomputerscience.org"` |  |
| isaac-code-editor.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-code-editor.ingress.path | string | `"/"` |  |
| isaac-code-editor.resources | object | `{}` |  |
| isaac-code-editor.service.type | string | `"ClusterIP"` |  |
| isaac-content-editor.containerPorts.http | int | `80` |  |
| isaac-content-editor.extraEnvVars[0].name | string | `"REACT_APP_SITE"` |  |
| isaac-content-editor.extraEnvVars[0].value | string | `"CS"` |  |
| isaac-content-editor.extraEnvVars[1].name | string | `"REACT_APP_CLIENT_ID"` |  |
| isaac-content-editor.extraEnvVars[1].value | string | `"f1540415e26cc2a5765a"` |  |
| isaac-content-editor.extraEnvVars[2].name | string | `"REACT_APP_AUTH_URL"` |  |
| isaac-content-editor.extraEnvVars[2].value | string | `"https://editor-auth.non-prod.isaaccomputerscience.org/access_token"` |  |
| isaac-content-editor.extraEnvVars[3].name | string | `"REACT_APP_GITHUB_OWNER"` |  |
| isaac-content-editor.extraEnvVars[3].value | string | `"isaaccomputerscience"` |  |
| isaac-content-editor.extraEnvVars[4].name | string | `"REACT_APP_CONTENT_REPO"` |  |
| isaac-content-editor.extraEnvVars[4].value | string | `"rutherford-content"` |  |
| isaac-content-editor.extraEnvVars[5].name | string | `"REACT_APP_PREVIEW_HOST"` |  |
| isaac-content-editor.extraEnvVars[5].value | string | `"https://editor-preview.non-prod.isaaccomputerscience.org"` |  |
| isaac-content-editor.extraEnvVars[6].name | string | `"REACT_APP_API_STAGING_HOST"` |  |
| isaac-content-editor.extraEnvVars[6].value | string | `"https://www.staging.non-prod.isaaccomputerscience.org"` |  |
| isaac-content-editor.extraEnvVars[7].name | string | `"REACT_APP_API_HOST"` |  |
| isaac-content-editor.extraEnvVars[7].value | string | `"https://www.non-prod.isaaccomputerscience.org"` |  |
| isaac-content-editor.image.registry | string | `"ghcr.io"` |  |
| isaac-content-editor.image.repository | string | `"isaaccomputerscience/isaac-content-editor"` |  |
| isaac-content-editor.image.tag | string | `"v1.0.0"` |  |
| isaac-content-editor.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| isaac-content-editor.ingress.annotations."nginx.ingress.kubernetes.io/configuration-snippet" | string | `"more_set_headers \"default-src 'self' https://cdn.non-prod.isaaccomputerscience.org https://staging.non-prod.isaaccomputerscience.org https://www.youtube-nocookie.com https://www.youtube.com https://api.github.com https://editor-auth.non-prod.isaaccomputerscience.org object-src 'none'; frame-src 'self' https://editor-preview.non-prod.isaaccomputerscience.org https://content-editor.non-prod.isaaccomputerscience.org https://www.youtube-nocookie.com; img-src 'self' data: https://cdn.non-prod.isaaccomputerscience.org https://*.tile.openstreetmap.org https://developers.google.com; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src 'self' https://cdn.non-prod.isaaccomputerscience.org https://fonts.gstatic.com;\";\n"` |  |
| isaac-content-editor.ingress.enabled | bool | `true` |  |
| isaac-content-editor.ingress.extraTls[0].hosts[0] | string | `"content-editor.non-prod.isaaccomputerscience.org"` |  |
| isaac-content-editor.ingress.extraTls[0].secretName | string | `"content-editor-isaac"` |  |
| isaac-content-editor.ingress.hostname | string | `"content-editor.non-prod.isaaccomputerscience.org"` |  |
| isaac-content-editor.ingress.ingressClassName | string | `"nginx"` |  |
| isaac-content-editor.ingress.path | string | `"/"` |  |
| isaac-content-editor.resources | object | `{}` |  |
| isaac-content-editor.service.type | string | `"ClusterIP"` |  |
| nameOverride | string | `""` |  |

----------------------------------------------
