# Lab 2: Working with Identity Environment Files in OpenStack

## Objective

Master the use of identity environment files to manage connections to the undercloud and overcloud.

## Tasks

### 1. Create and Configure Identity Environment Files

**Undercloud RC file** (`undercloudrc`):
```bash
cat <<EOF > undercloudrc
export OS_AUTH_URL=http://<undercloud-ip>:5000/v3
export OS_IDENTITY_API_VERSION=3
export OS_PROJECT_NAME=admin
export OS_PROJECT_DOMAIN_NAME=Default
export OS_USERNAME=admin
export OS_USER_DOMAIN_NAME=Default
export OS_PASSWORD=<admin-password>
EOF
```

**Overcloud RC file** (`overcloudrc`):
```bash
cat <<EOF > overcloudrc
export OS_AUTH_URL=http://<overcloud-ip>:5000/v3
export OS_IDENTITY_API_VERSION=3
export OS_PROJECT_NAME=admin
export OS_PROJECT_DOMAIN_NAME=Default
export OS_USERNAME=admin
export OS_USER_DOMAIN_NAME=Default
export OS_PASSWORD=<admin-password>
EOF
```

### 2. Use Files to Connect to the Undercloud and Overcloud

```bash
# Source the undercloud file and verify
source undercloudrc
openstack image list

# Source the overcloud file and verify
source overcloudrc
openstack image list
```

## Conclusion

Participants are now proficient in creating, sourcing, and verifying identity environment files
for OpenStack undercloud and overcloud connections.
