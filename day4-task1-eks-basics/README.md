# Day 4 - Task 1: Kubernetes Basics (EKS)

## Objective

Deploy a multi-pod application on EKS using deployment and service manifests.

## Setup

- Cluster: devops-intern-cluster (created via eksctl, us-east-1)
- Node group: devops-intern-nodes (2x t3.small, managed)
- IAM roles for cluster and nodes created manually via console to
understand the EKS trust model (control plane vs worker node roles)

## Manifests

See deployment.yaml (3 replicas, nginx:alpine) and service.yaml
(LoadBalancer type).

## Verification

```bash
kubectl get nodes
kubectl get pods
kubectl get svc
curl http://<external-hostname>
```

3 pods Running, LoadBalancer service live, nginx welcome page returned
successfully.

## Screenshots

See `/screenshots` folder.

## Key Takeaway

EKS's cluster-authentication layer (mapping IAM roles to Kubernetes RBAC  
groups) is a distinct concern from IAM permissions or VPC networking -  
easy to miss building infrastructure manually rather than through  
purpose-built tooling like eksctl.