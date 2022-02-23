# Kubernetes API Object Model And Types

API Version | Object Kind/Type | Description
------------|-----------------|-------------
v1 | Namespace | Logical group of objects
v1 | ConfigMap | Collection of Key/Value pairs used for storing configuration for application.
v1 | Secret | Configuration values (Key/Value pairs) or Digital Certificates or User-credentials. All values are encoded using `base64`.
v1 | Pod | Wrapper for container(s). Minimum ONE container per pod. Pods are treated like a cattle and not as pet. All other API Objects either are linked to Pods.
