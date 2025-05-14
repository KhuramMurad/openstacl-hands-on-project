# Lab 8: Networking Configuration in OpenStack

## Objective

Configure project networks, routers, and Open Virtual Networks (OVN) in OpenStack.

## Tasks

### 1. Create and Assign Networks to Projects

```bash
# Create a network and subnet
openstack network create network-name
openstack subnet create --network network-id --subnet-range subnet-range --gateway gateway-ip subnet-name

# List networks and subnets
openstack network list
openstack subnet list

# Attach network to a project
openstack network set --project project-id network-id
```

### 2. Configure Network Routers

```bash
# Create and list routers
openstack router create router-name
openstack router list

# Add interfaces and set external gateway
openstack router add subnet router-id subnet-id
openstack router set --external-gateway external-network-id router-id
```

### 3. Work with Open Virtual Networks (OVN)

```bash
# Install OVN components
sudo yum install -y openvswitch ovn-northd ovn-central

# Start services
sudo systemctl start openvswitch ovn-northd ovn-central

# Create and list OVN logical switches
ovn-nbctl ls-add ovn-switch
ovn-nbctl ls-list
```

## Conclusion

Participants can now set up complex networking, including project isolation and advanced OVN switches.
