# Automated Infrastructure with Ansible and Vagrant

## Overview

This project automates the deployment and configuration of a complete Linux infrastructure using Ansible and Vagrant.

The infrastructure includes:

* HAProxy for load balancing
* Keepalived for high availability (HA)
* Prometheus for metrics collection and monitoring
* Node Exporter for system metrics
* Grafana for visualization and dashboards
* SSL/TLS configuration for secure communications

## Objectives

The main goal of this project is to demonstrate Infrastructure as Code (IaC) practices by automating the provisioning, configuration, monitoring, and security of multiple servers.

## Architecture

The environment consists of:

* 1 Ansible control node
* Multiple backend servers
* 2 HAProxy load balancers
* Keepalived for failover and virtual IP management
* Prometheus monitoring server
* Grafana dashboard server

## Technologies Used

* Ansible
* Vagrant
* Linux
* HAProxy
* Keepalived
* Prometheus
* Grafana
* Node Exporter
* SSL/TLS

## Learning Outcomes

Through this project, I gained practical experience with:

* Infrastructure as Code (IaC)
* Configuration Management
* High Availability Architecture
* Monitoring and Observability
* Linux System Administration
* Network Load Balancing
* Security Hardening
* Automation and DevOps Practices

## Project Structure

```text
inventory/
└── hosts.ini

playbooks/
├── grafana.yml
├── haproxy.yml
├── haproxy2.yml
├── ngix.yml
├── node_exporter.yml
├── prometheus.yml
├── securisation_grafana.yml
├── prometheus.service.j2
├── load balancing/
│   ├── keepalived.yml
│   └── load_balancing.yml
└── ssl_project/
    ├── ca.yml
    └── securisationSsl.yml

README.md
Vagrantfile
```

## Features

### Load Balancing

* Automated HAProxy installation and configuration
* Traffic distribution across backend servers
* High availability setup using Keepalived

### Monitoring

* Prometheus deployment and configuration
* Node Exporter installation on monitored servers
* Grafana dashboards for infrastructure visualization

### Security

* SSL/TLS certificate generation and deployment
* Secure Grafana configuration
* Encrypted communication between services

### Automation

* Fully automated server configuration with Ansible
* Reproducible virtual environment using Vagrant
* Centralized inventory management

## Deployment

Start the virtual machines:

```bash
vagrant up
```

Verify connectivity:

```bash
ansible all -i inventory/hosts.ini -m ping
```

Run a playbook:

```bash
ansible-playbook -i inventory/hosts.ini playbooks/prometheus.yml
```


