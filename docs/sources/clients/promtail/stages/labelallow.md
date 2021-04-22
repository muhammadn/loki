---
title: labelallow
---
# `labelallow` stage

The labelallow stage is an action stage that allows only the provided labels 
to be included in the label set that is sent to Loki with the log entry.

## Schema

```yaml
labelallow:
  - [<string>]
  ...
```

### Examples

For the given pipeline:

```yaml
kubernetes_sd_configs:
 - role: pod 
pipeline_stages:
- docker: {}    
- labelallow:
    - kubernetes_pod_name
    - kubernetes_container_name
```

Given the following incoming labels:

- `kubernetes_pod_name`: `"loki-pqrs"`
- `kubernetes_container_name`: `"loki"`
- `kubernetes_pod_template_hash`: `"79f5db67b"`
- `kubernetes_controller_revision_hash`: `"774858987d"`

Only the below labels would be sent to `loki`

- `kubernetes_pod_name`: `"loki-pqrs"`
<<<<<<< HEAD
- `kubernetes_container_name`: `"loki"`
=======
- `contaikubernetes_container_namener`: `"loki"`
>>>>>>> 4c334c8e11be3a29314cddaf7fb74f6ff89bac21
