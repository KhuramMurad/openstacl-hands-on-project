# Lab 4: Configuring Applications for Reliability

## Objective

Configure health probes, resource requests/limits, and scaling to ensure application reliability.

## Tasks

### 1. Implement Liveness and Readiness Probes

Create `my-app-deployment.yaml`:
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app-container
        image: my-app-image
        livenessProbe:
          httpGet:
            path: /healthz
            port: 8080
        readinessProbe:
          httpGet:
            path: /readiness
            port: 8080
```

### 2. Set Resource Requests and Limits

Create `my-pod.yaml`:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
  - name: my-container
    image: my-container-image
    resources:
      requests:
        memory: "64Mi"
        cpu: "250m"
      limits:
        memory: "128Mi"
        cpu: "500m"
```

### 3. Scale Manually and Configure Autoscaling

```bash
# Scale deployment
oc scale deployment my-app --replicas=5

# Configure autoscaling based on CPU utilization
oc autoscale deployment my-app --cpu-percent=70 --min=3 --max=10
```

## Conclusion

Participants have learned to configure probes, set resource boundaries,
and scale applications for reliability.
