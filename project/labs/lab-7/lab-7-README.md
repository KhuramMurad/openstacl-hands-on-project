# Lab 7: Monitoring and Logging

## Objective

Configure monitoring tools, fetch logs, and set alerts in OpenShift.

## Tasks

### 1. Configure and Use Monitoring Tools

```bash
# Deploy Prometheus and Grafana via cluster-monitoring-operator
oc apply -f https://github.com/openshift/cluster-monitoring-operator/releases/download/v0.10.0/cluster-monitoring.yaml

# Forward Grafana port
oc port-forward -n openshift-monitoring service/grafana 3000
```

### 2. Fetch and Analyze Logs

```bash
# Fetch pod logs
oc logs pod/my-pod

# Fetch container logs within a pod
oc logs pod/my-pod -c my-container
```

### 3. Set Up Alerts

```bash
oc create alert my-cpu-alert --expr '100 * (1 - avg(rate(container_cpu_usage_seconds_total{container_name!="POD",pod_name=~"my-pod"}[5m])) by (pod_name, namespace) / on (pod_name, namespace) group_left sum(kube_pod_container_resource_limits_cpu_cores) * 100) > 90'
```

## Conclusion

Participants are now equipped to monitor cluster health, analyze logs,
and configure alerts for proactive maintenance.
