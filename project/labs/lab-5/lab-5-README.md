# Lab 5: Configuring OpenStack Domains, Projects, and Users

## Objective

Manage domains, projects, and user accounts in OpenStack.

## Tasks

### 1. Configure OpenStack Domains

```bash
# Create and list domains
openstack domain create --description "Domain Description" domain-name
openstack domain list
```

### 2. Create and Manage Projects

```bash
# Create a project
openstack project create --domain domain-name --description "Project Description" project-name

# List and update projects
openstack project list --domain domain-name
openstack project set --description "New Project Description" project-id
```

### 3. Create User Accounts and Assign Roles

```bash
# Create and list users
openstack user create --domain domain-name --password-prompt username
openstack user list --domain domain-name

# Assign role to user on project
openstack role add --user user-id --project project-id --user-domain domain-name --project-domain domain-name role-name
```

## Conclusion

Participants can now configure domains, manage projects, and set user permissions
for secure access control.
