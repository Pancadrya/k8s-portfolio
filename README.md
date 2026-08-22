# 🚀 Enterprise-Grade Kubernetes Local Lab (3-Tier Architecture)

This repository showcases a complete, production-simulated local Kubernetes environment. It demonstrates the deployment of a 3-tier application using advanced Site Reliability Engineering (SRE) and DevOps practices.

## 🏗️ Architecture & Tech Stack

- **Infrastructure:** Kubernetes in Docker (KinD) - 1 Control Plane, 2 Worker Nodes.
- **Routing:** NGINX Ingress Controller for path-based routing.
- **Workloads:** Stateless Deployments (Frontend, Backend) & StatefulSet (PostgreSQL).
- **Configuration:** Decoupled configs using Kubernetes ConfigMaps and Secrets.
- **Autoscaling:** Horizontal Pod Autoscaler (HPA) integrated with Metrics Server.
- **Package Management:** Helm v3 for dynamic, reusable deployments.
- **Observability:** Prometheus & Grafana stack (Diet-mode via Helm).
- **CI/CD:** GitHub Actions with Self-Hosted Runner for automated Helm deployments.

## 💡 Key Highlights

1. **Zero-Downtime Deployments:** Configured Readiness and Liveness probes to ensure graceful rollouts without dropping user requests.
2. **Dynamic Templating (Helm):** Converted static, hardcoded YAMLs into a reusable `portfolio-chart` for multi-environment deployments.
3. **Automated CI/CD Pipeline:** Implemented a GitHub Actions workflow that automatically upgrades the Helm release in the local cluster upon code push.
4. **Stateful Data Persistence:** Bound the PostgreSQL database to local storage via Persistent Volume Claims (PVC), ensuring data survival across pod restarts.
