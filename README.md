# To Do Web App

This project demonstrates how to containerize and deploy a full-stack To-Do web application using Flask and MongoDB across Kubernetes environments. It includes deployments on **Minikube (local)** and **AWS EKS (cloud)**, with advanced Kubernetes features such as replication controllers, rolling updates, health probes, and optional alerting using Prometheus and Slack.

---

## 📌 Project Structure

1. **Frontend**: Simple To-Do app UI served using Flask.
2. **Backend**: Flask app connected to a MongoDB instance.
3. **Database**: MongoDB container with persistent storage.
4. **Deployment Targets**: Minikube (local) and Amazon EKS (cloud).
5. **Alerting**: Prometheus + Slack integration for system alerts (Extra Credit).

---

## 🛠️ Prerequisites

- Docker installed
- Minikube & kubectl configured
- AWS CLI configured
- DockerHub account
- Basic understanding of Kubernetes & Docker

---

## 🚀 Steps

### ✅ Part 1: Application Creation
- Build a simple Flask-based To-Do application.
- Use MongoDB to persist data.

### ✅ Part 2: Dockerization
- Create a `Dockerfile` for the Flask app.
- Use `docker-compose.yml` to spin up Flask and MongoDB containers.
- Push the Docker image to DockerHub.

### ✅ Part 3: Deploy on Minikube
- Start Minikube.
- Deploy the app using Kubernetes manifests (Deployment + Service).
- Create 2 Pods (Flask + MongoDB).
- Expose the Flask service to access from the browser.
- Test locally via Minikube IP.

### ✅ Part 4: Deploy on AWS EKS
- Create an EKS Cluster via AWS Console or CLI.
- Connect using `kubectl`.
- Deploy the same app using the image from DockerHub.
- Expose it using a LoadBalancer-type Service.
- Verify external access and scaling.

### ✅ Part 5: Replication Controller
- Create a ReplicationController to maintain desired Pod count.
- Test auto-recovery by deleting a pod and verifying that it restarts.
- Scale up/down by modifying the replica count.

### ✅ Part 6: Rolling Updates
- Configure rolling update strategy in your Deployment.
- Set `maxUnavailable` and `maxSurge`.
- Update the Docker image version and apply changes.
- Monitor using `kubectl rollout status`.

### ✅ Part 7: Health Monitoring
- Add **Liveness** and **Readiness Probes** in the pod spec.
- Configure endpoints and failure thresholds.
- Test with intentional errors and verify self-healing behavior.

---

## 🌐 Extra Credit (20 Points): Alerting

### 🛎️ Prometheus + Slack Alerting Setup

- Deploy **Prometheus** in the cluster.
- Configure `alertmanager.yml` to send alerts to a Slack webhook.
- Define alert rules (e.g., high failure rate in liveness probes).
- Test by causing pod failures.
- Verify that alerts are delivered to the Slack channel.

---

## 📁 Submission Checklist

- ✅ `Dockerfile`
- ✅ `docker-compose.yml`
- ✅ Kubernetes manifests: Deployment, Service, ReplicationController, Probes
- ✅ Screenshots of:
  - App running on Minikube
  - App running on AWS EKS
  - Alert received on Slack (optional)
- ✅ Document with explanation of each step (this file can serve that purpose)

---

## 🔗 Useful Links

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Minikube Installation](https://minikube.sigs.k8s.io/docs/start/)
- [AWS EKS Guide](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html)
- [Prometheus Docs](https://prometheus.io/)
- [Kubernetes Probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)

---

## 🧠 Authors

*Name*: Nitisha Shetty 
*Course*: Cloud Computing and Big Data Systems  
*Term*: Fall 2024  

---

## 💬 Questions?

Raise an issue in the GitHub repo or contact via Slack!
