# Lab 6: Managing Quotas and Resources in OpenStack

## Objective

Set up and manage project quotas and create custom VM flavors.

## Tasks

### 1. Manage Quotas

```bash
# Set quotas for a project
openstack quota set --instances 10 --volumes 20 --gigabytes 100 --project project-id

# Show quotas
openstack quota show project-id
```

### 2. Create and Manage Flavors

```bash
# Create a custom flavor
openstack flavor create --ram 4096 --disk 40 --vcpus 2 --public flavor-name

# List, show, and delete flavors
openstack flavor list
openstack flavor show flavor-id
openstack flavor delete flavor-id
```

## Conclusion

Participants can now enforce resource limits and customize instance flavors
for optimal resource management.
