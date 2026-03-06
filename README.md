# DevOps Microservices Implementation on AWS

This project demonstrates a **production-style DevOps implementation**
for deploying a cloud‑native microservices application on **AWS EKS**
using modern DevOps tools and best practices.

The application represents a **retail e‑commerce platform**, similar to
systems used by companies like Amazon or Shopify. It consists of
multiple microservices built with different programming languages and
backed by various databases and messaging systems.

The goal of this project is to simulate a **real-world DevOps
environment**, covering the full lifecycle from containerization and
infrastructure provisioning to Kubernetes deployment, observability, and
CI/CD automation.

------------------------------------------------------------------------

## Application Architecture

The retail store application consists of **five microservices**:

  Service    Technology    Responsibility
  ---------- ------------- -------------------------------
  Catalog    Go            Product listing and inventory
  Cart       Spring Boot   Shopping cart operations
  Checkout   Node.js       Payment processing
  Orders     Spring Boot   Order management
  UI         Java          Customer-facing web interface

The application uses several data services:

-   MySQL
-   PostgreSQL
-   DynamoDB
-   Redis
-   RabbitMQ / SQS

These services simulate a **real microservices data architecture**.

------------------------------------------------------------------------

## Project Architecture

The project deploys **10 containerized components** in an **AWS EKS
Kubernetes cluster**, including:

-   5 Microservices
-   3 Databases
-   1 Cache system
-   1 Messaging system

The architecture evolves from **self-hosted services inside Kubernetes**
to **fully managed AWS services**.

------------------------------------------------------------------------

## Technologies Used

### Containerization

-   Docker
-   Dockerfiles
-   Multi-stage builds
-   Multi-platform builds
-   Docker Compose

### Infrastructure as Code

-   Terraform
-   VPC provisioning
-   Remote state management
-   Terraform modules

### Kubernetes

-   AWS EKS
-   Pods
-   Deployments
-   Services
-   StatefulSets
-   ConfigMaps
-   Secrets
-   Persistent Volumes

### Kubernetes Add-ons

-   AWS Load Balancer Controller
-   External DNS
-   EBS CSI Driver
-   Secrets Store CSI Driver
-   Pod Identity Agent

### Package Management

-   Helm
-   Helm Charts
-   Helm Templates
-   Helm Releases

### AWS Services

-   EKS
-   RDS
-   DynamoDB
-   ElastiCache
-   SQS
-   Route53
-   ACM
-   ECR

### Observability

-   OpenTelemetry
-   AWS X-Ray
-   CloudWatch Logs
-   Amazon Managed Prometheus
-   Amazon Managed Grafana

### Auto Scaling

-   Karpenter (Node Autoscaling)
-   Horizontal Pod Autoscaler

### CI/CD & GitOps

-   GitHub Actions
-   ArgoCD
-   Helm deployments
-   GitOps workflows

------------------------------------------------------------------------

## DevOps Pipeline

This project implements a **complete CI/CD GitOps workflow**.

### Continuous Integration

GitHub Actions pipeline:

1.  Checkout source code
2.  Build Docker images
3.  Push images to **AWS ECR**
4.  Update Helm chart image tags

### Continuous Delivery (GitOps)

ArgoCD continuously monitors the repository and automatically deploys
changes to the **EKS cluster**.

    GitHub → GitHub Actions → AWS ECR → Helm Charts → ArgoCD → AWS EKS

------------------------------------------------------------------------

## Observability & Monitoring

The project implements **modern observability using OpenTelemetry**.

Metrics, logs, and traces are collected and sent to:

-   Amazon Managed Prometheus
-   Amazon Managed Grafana
-   AWS X-Ray
-   CloudWatch Logs

------------------------------------------------------------------------

## Cost Optimization

The infrastructure uses **Karpenter Node Autoscaling** with Spot
instances.

This enables **70--85% infrastructure cost savings** while maintaining
application availability.

------------------------------------------------------------------------

## Learning Objectives

This project demonstrates how to:

-   Build containerized microservices with Docker
-   Provision cloud infrastructure with Terraform
-   Deploy applications to Kubernetes (AWS EKS)
-   Manage Kubernetes packages with Helm
-   Implement CI/CD pipelines with GitHub Actions
-   Deploy applications using GitOps with ArgoCD
-   Implement observability with OpenTelemetry
-   Configure auto-scaling with Karpenter
-   Integrate Kubernetes workloads with AWS managed services

------------------------------------------------------------------------

## Repository Structure

    sections
    ├── terraform-vpc
    ├── terraform-eks
    ├── docker-images
    ├── kubernetes-manifests
    ├── helm-charts
    ├── autoscaling-karpenter
    ├── observability-otel
    └── cicd-github-actions-argocd

------------------------------------------------------------------------

## Project Goal

This project addresses the challenge of deploying and managing complex cloud-native applications by implementing a real-world DevOps platform that automates infrastructure, application deployment, and operational management in production environments.

