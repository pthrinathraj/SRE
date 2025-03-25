# 📘 Site Reliability Engineering (SRE) – Tools & Technologies

This document outlines the core tools, technologies, and practices essential for modern Site Reliability Engineers (SREs). Tools are grouped by category and aligned with real-world responsibilities across reliability, automation, observability, security, and infrastructure.

---

## ⚙️ Core SRE & DevOps Tools

| Tool/Technology | Description |
|-----------------|-------------|
| **Linux**       | Foundation for server administration, scripting, performance tuning, and debugging. |
| **Git**         | Distributed version control system for source code management and collaboration. |
| **Jenkins**     | Automation server used to build, test, and deploy CI/CD pipelines. |
| **Maven / Gradle** | Build tools for Java-based applications; dependency and lifecycle management. |
| **Ansible**     | Agentless configuration management and automation using YAML playbooks. |
| **Terraform**   | Infrastructure as Code (IaC) tool to provision and manage cloud resources. |
| **Helm**        | Kubernetes package manager for deploying, upgrading, and managing applications. |
| **GitOps (ArgoCD, Flux)** | Git-driven operations and continuous delivery for Kubernetes workloads. |

---

## 🐳 Containerization & Orchestration

| Tool/Technology | Description |
|-----------------|-------------|
| **Docker**      | Platform to build, package, and run containerized applications. |
| **Kubernetes**  | Orchestration platform for containerized workloads and services. |
| **Istio**       | Service mesh for advanced traffic routing, observability, and security in Kubernetes. |
| **Helm**        | (Also listed above) Package manager for Kubernetes applications. |
| **Service Discovery** | Dynamically registers and locates microservices (e.g., Kubernetes DNS, Consul). |

---

## 📊 Observability: Monitoring, Logging, and Alerting

| Tool/Technology | Description |
|-----------------|-------------|
| **Prometheus**  | Monitoring and alerting toolkit with time-series data collection. |
| **Grafana**     | Open-source platform for visualizing metrics from various data sources. |
| **Alertmanager / Sensu** | Alert routing and deduplication system often used with Prometheus. |
| **Splunk**      | Log aggregation, analysis, and visualization platform. |
| **ELK Stack**   | Elasticsearch, Logstash, and Kibana for log management and analytics. |
| **Monitoring & Alerting** | Strategies and tools to ensure system health and uptime. |
| **Logging & Log Management** | Centralized log storage, indexing, and querying. |

---

## ☁️ Cloud Platforms & Infrastructure

| Tool/Technology | Description |
|-----------------|-------------|
| **AWS**         | Widely used cloud service provider; includes compute, storage, networking, and more. |
| **Networking**  | Core concepts such as TCP/IP, DNS, VPNs, Subnetting, NAT, firewalls, etc. |
| **Load Balancing (HAProxy, Envoy)** | Distributes network traffic across multiple servers or services. |
| **Secrets Management (Vault, AWS Secrets Manager)** | Secure storage and access of sensitive data. |
| **Configuration Management (Puppet, Chef)** | Automates system configuration across infrastructure. |
| **Infrastructure Automation** | Provisioning and management using code and automation tools. |

---

## 🔐 Security & Resilience

| Tool/Technology | Description |
|-----------------|-------------|
| **Container Security (Trivy, Aqua)** | Scanning, vulnerability detection, and runtime protection. |
| **Secrets Management** | Secure handling of tokens, passwords, and credentials. |

---

## 🛠️ Developer Experience & Pipelines

| Tool/Technology | Description |
|-----------------|-------------|
| **CI/CD Pipelines** | Automate software delivery from development to production. |
| **GitOps**      | Operational model using Git as the source of truth for infrastructure and applications. |
| **Build Tools (Maven, Gradle)** | (Also listed above) Application builds and dependency management. |

---

## 🚨 Incident Management & Reliability

| Tool/Technology | Description |
|-----------------|-------------|
| **PagerDuty / Blameless** | On-call alerting, incident management, and postmortems. |
| **Incident Management & RCA** | Frameworks to respond to incidents and analyze root causes. |

---

## 🗃️ Databases

| Type | Examples |
|------|----------|
| **SQL** | MySQL, PostgreSQL |
| **NoSQL** | MongoDB, Cassandra |
| **In-Memory** | Redis, Memcached |

---

## ✅ How to Use This Guide

Use this document to:
- **Map your expertise** across critical SRE areas.
- **Build structured learning paths** or internal training docs.
- **Prepare for interviews** and team discussions.
- **Plan observability, automation, and CI/CD strategies. |
