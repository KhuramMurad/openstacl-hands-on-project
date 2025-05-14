# Lab 3: Utilizing Template and Environment Files in OpenStack

## Objective

Understand and utilize Heat Orchestration Templates (HOT) and environment files to define and deploy OpenStack resources.

## Tasks

### 1. Create a Heat Orchestration Template

Create `example.yaml`:
```yaml
heat_template_version: 2013-05-23

resources:
  my_instance:
    type: OS::Nova::Server
    properties:
      name: my_instance
      image: <image-id>
      flavor: <flavor-id>
```

### 2. Create an Environment File

Create `environment.yaml`:
```yaml
resource_registry:
  "OS::Nova::Server": "my_instance.yaml"
```

### 3. Deploy the Stack

```bash
openstack stack create -t example.yaml -e environment.yaml my_stack
```

### 4. Extract and Analyze Information

```bash
openstack stack list
openstack stack show my_stack
openstack stack resource list my_stack
openstack stack resource show my_stack my_instance
```

## Conclusion

Participants can now create HOT templates and environment files,
deploy a stack, and analyze the resulting resources.
