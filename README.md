# OpenStack Hands-On Project

A comprehensive, step-by-step collection of hands-on labs for deploying, configuring, and managing an OpenStack cloud environment using TripleO, Heat, and the OpenShift/OC CLI. Whether you’re just getting started with director-based deployments or diving into advanced networking, monitoring, and reliability, this repo walks you through exactly what you need to know—commands, templates, environment files, and best practices included.

---

## 📖 Table of Contents

- [OpenStack Hands-On Project](#openstack-hands-on-project)
  - [📖 Table of Contents](#-table-of-contents)
  - [Overview](#overview)
  - [Labs Included](#labs-included)
  - [Prerequisites](#prerequisites)
  - [Lab Environment Setup](#lab-environment-setup)
  - [Project Structure](#project-structure)
  - [Getting Started](#getting-started)
  - [How to Work Through the Labs](#how-to-work-through-the-labs)
  - [Contributing](#contributing)
  - [About the Author](#about-the-author)
  - [License](#license)

---

## Overview

This repository is designed for DevOps and Cloud Engineers who want hands-on experience with:
- **Director-Based Deployments** (TripleO undercloud/overcloud)  
- **Identity & Environment Files** (undercloudrc, overcloudrc)  
- **Heat Orchestration Templates** & environment overrides  
- **Application Reliability** (liveness/readiness probes, autoscaling)  
- **Keystone Domains, Projects & Users**  
- **Quota Management & Custom Flavors**  
- **Monitoring & Logging** (Prometheus, Grafana, alerts)  
- **Networking with OpenStack Neutron & OVN**

Each lab is self-contained under `labs/lab-<n>/lab-<n>-README.md` with full commands, YAML snippets, and explanations.

---

## Labs Included

| Lab   | Title                                                      |
| :---: | :--------------------------------------------------------- |
| 1     | Director-Based Deployments in OpenStack                    |
| 2     | Working with Identity Environment Files                    |
| 3     | Utilizing Template & Environment Files (Heat)              |
| 4     | Configuring Applications for Reliability                   |
| 5     | Configuring OpenStack Domains, Projects & Users            |
| 6     | Managing Quotas & Resources                                |
| 7     | Monitoring & Logging                                       |
| 8     | Networking Configuration (Neutron & OVN)                   |

---

## Prerequisites

- A running OpenStack **undercloud** (TripleO) and **overcloud**  
- `python-tripleoclient`, `openstackclient`, `oc` (OpenShift CLI)  
- `kubectl` (if testing on a Kubernetes-backed overcloud)  
- Access to the undercloud & overcloud endpoints (credentials in RC files)  
- Administrator (sudo) privileges on your lab host

---

## Lab Environment Setup

To set up your environment to perform all labs end-to-end, follow these steps:

1. **Control Host Requirements**  
   - OS: RHEL 8/CentOS 8 or Ubuntu 20.04 LTS (64‑bit)  
   - Minimum: 8 GB RAM, 4 CPU cores, 50 GB disk space  
   - Network: Internet access and connectivity between control and lab nodes

2. **Install CLI Tools**  
   ```bash
   # On RHEL/CentOS:
   sudo yum install -y python3-tripleoclient python3-openstackclient
   # On Ubuntu:
   sudo apt update
   sudo apt install -y python3-tripleoclient python3-openstackclient

   # OpenShift CLI (oc) and kubectl:
   curl -sL https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux.tar.gz \
     | tar xz -C /usr/local/bin oc kubectl

   # Kubernetes CLI:
   sudo apt install -y kubectl
   ```

3. **Configure Host Machine**  
   - Enable or open firewall rules for required ports (5000, 80, 443).  
   - Ensure passwordless SSH (public key) between control host and undercloud/overcloud nodes.

4. **Prepare Undercloud Node**  
   - Set hostname and static IP according to lab instructions.  
   - (Optional) Disable NetworkManager if using static network configuration:
     ```bash
     sudo systemctl disable NetworkManager
     sudo systemctl stop NetworkManager
     ```

5. **Create and Source RC Files**  
   - Follow Lab 2 to generate `undercloudrc` and `overcloudrc` with correct endpoints and credentials:
     ```bash
     source undercloudrc
     source overcloudrc
     ```

6. **Verify Environment**  
   ```bash
   openstack image list
   oc version
   kubectl version --client
   ```

Once complete, you’re ready to start with Lab 1.

---

## Project Structure

```
.
├── LICENSE
├── README.md
└── labs
    ├── lab-1
    │   └── lab-1-README.md
    ├── lab-2
    │   └── lab-2-README.md
    ├── lab-3
    │   └── lab-3-README.md
    ├── lab-4
    │   └── lab-4-README.md
    ├── lab-5
    │   └── lab-5-README.md
    ├── lab-6
    │   └── lab-6-README.md
    ├── lab-7
    │   └── lab-7-README.md
    └── lab-8
        └── lab-8-README.md
```

---

## Getting Started

1. **Clone the repo**  
   ```bash
   git clone https://github.com/KhuramMurad/openstacl-hands-on-project.git
   cd openstacl-hands-on-project
   ```

2. **Browse the labs folder**  
   Each lab directory contains a self-contained `README.md` with objectives, steps, and examples.

3. **Follow the instructions**  
   Source your undercloud/overcloud RC files, apply templates, run `openstack` or `oc` commands, and verify results.

---

## How to Work Through the Labs

- **One lab at a time**: Read the objectives, prerequisites, and complete each task sequentially.  
- **Verify results**: Use `openstack` or `oc` subcommands to ensure each resource is created and configured correctly.  
- **Experiment & extend**: Change probe paths, flavor sizes, quotas, or network CIDRs to match your own environment.

---

## Contributing

Contributions are welcome! If you find errors or have enhancements:

1. Fork the repo  
2. Create a feature branch (`git checkout -b feature/awesome-lab`)  
3. Commit your changes (`git commit -m "Add advanced OVN tutorial"`)  
4. Push to your branch (`git push origin feature/awesome-lab`)  
5. Open a Pull Request

Please follow the existing style, add meaningful examples, and update this `README.md` if you add new labs.

---

## About the Author

This project is maintained by **Khuram Murad**,  
**AIOps Engineer** at **Al Nafi International College**.  
I build and automate cloud-native and AI-driven operations, and I hope these labs help you accelerate your OpenStack journey!

---

## License

This project is licensed under the [MIT License](LICENSE).  
Feel free to use, modify, and share!
