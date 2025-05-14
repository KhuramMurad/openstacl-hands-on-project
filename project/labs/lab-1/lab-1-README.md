# Lab 1: Director-Based Deployments in OpenStack

## Objective

The objective of this lab is to help participants understand the architecture and
workflow of director-based deployments in OpenStack. Participants will explore
components and services involved in a director-based deployment and set up a
basic director environment.

## Tasks

### 1. Explore Components and Services
- **Director**: Responsible for deploying and managing OpenStack services using TripleO.
- **Undercloud**: Single-node OpenStack deployment used to manage and deploy the overcloud.
- **Overcloud**: The actual OpenStack cloud deployed and managed by the director.
- **Heat**: Orchestration service used by the director.
- **Ironic**: Bare-metal provisioning service.

### 2. Set Up a Basic Director Environment

1. **Install director packages**:
```bash
sudo yum install -y python-tripleoclient
```

2. **Generate undercloud configuration**:
```bash
openstack undercloud install --config undercloud.conf
```
Edit `undercloud.conf` as needed (e.g., local IPs, network settings).

3. **Install and configure the undercloud**:
```bash
openstack undercloud install
```

4. **Deploy the overcloud**:
```bash
openstack overcloud deploy
```

## Conclusion

Participants have gained foundational knowledge of director-based deployments
using TripleO, including setting up the undercloud and deploying the overcloud.
