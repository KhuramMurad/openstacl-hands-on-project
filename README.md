```markdown
# OpenStack Hands-On Project

A comprehensive, step-by-step collection of hands-on labs for deploying, configuring, and managing an OpenStack cloud environment using TripleO, Heat, and the OpenShift/OC CLI. Whether you’re just getting started with director-based deployments or diving into advanced networking, monitoring, and reliability, this repo walks you through exactly what you need to know—commands, templates, environment files, and best practices included.

---

## 📖 Table of Contents

1. [Overview]
2. [Labs Included]
3. [Prerequisites]
4. [Project Structure]  
5. [Getting Started]  
6. [How to Work Through the Labs]
7. [Contributing] 
8. [About the Author]
9. [License]

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
<!-- Future labs 9–12 coming soon! -->

---

## Prerequisites

- A running OpenStack **undercloud** (TripleO) and **overcloud**  
- `python-tripleoclient`, `openstackclient`, `oc` (OpenShift CLI)  
- `kubectl` (if testing on a Kubernetes-backed overcloud)  
- Access to the undercloud & overcloud endpoints (credentials in RC files)  
- Administrator (sudo) privileges on your lab host

---

## Project Structure

```
![image](https://github.com/user-attachments/assets/be0fd507-835e-4b31-9314-0ef150eef8b3)


````
````

---

## Getting Started

1. **Clone the repo**  
   ```bash
   git clone https://github.com/KhuramMurad/openstacl-hands-on-project.git
   cd openstacl-hands-on-project
````

2. **Browse the labs folder**
   Each lab directory contains a self-contained `README.md` with objectives, steps, and examples.

3. **Follow the instructions**
   Source your undercloud/overcloud RC files, apply templates, run `openstack` or `oc` commands, and verify results.

---

## How to Work Through the Labs

* **One lab at a time**: Read the objectives, prerequisites, and complete each task sequentially.
* **Verify results**: Use `openstack` or `oc` subcommands to ensure each resource is created and configured correctly.
* **Experiment & extend**: Change probe paths, flavor sizes, quotas, or network CIDRs to match your own environment.

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

```
