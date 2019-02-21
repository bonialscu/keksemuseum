# keksemuseum
This repo hosts k8s helm charts.

## Helm Renderer

### Initialize the Repo / Local Cache

```bash
$ helm init --client-only
$ helm repo remove local
$ helm dependency update apps/kekseapp
```

### Rendering

```bash
$ helm template apps/kekseapp \
    --set organizationbase.container.repository=myrepo/kekseapp \
    --set organizationbase.ingress.domain=example.com
```

### Applying

```bash
$ helm template apps/kekseapp \
    --set organizationbase.container.repository=myrepo/kekseapp \
    --set organizationbase.ingress.domain=example.com \
    | kubectl apply -f -
```
