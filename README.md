# Go Web App CI/CD Project 🚀

A fully automated **CI/CD pipeline** for a Go web application deployed on **Kubernetes (EKS)**.  
This project demonstrates end-to-end DevOps workflow: code → build → container → deploy → cluster → ingress.

## Overview
This project is a simple **full-stack application** with:
- **Frontend:** HTML / CSS / JavaScript (static)
- **Backend:** Go language

The goal was to automate deployment to **AWS EKS** using **GitHub Actions**, **Docker**, **Helm**, and **ArgoCD**.  

## Tech Stack
- **Language:** Go  
- **Frontend:** HTML, CSS, JavaScript  
- **Containerization:** Docker  
- **Orchestration:** Kubernetes (EKS)  
- **CI/CD:** GitHub Actions  
- **GitOps:** ArgoCD  
- **Deployment Management:** Helm charts  
- **Ingress:** NGINX Ingress Controller  
- **Cloud:** AWS (EKS, IAM, Security Groups)  
- **Secrets Management:** GitHub Secrets (GitHub token, DockerHub token)  

## Features
- Automated CI/CD pipeline triggered on `git push`  
- Go app build, test, Docker image creation, push to DockerHub  
- Helm charts for dynamic image version updates  
- ArgoCD automatically syncs Helm charts to EKS cluster  
- Kubernetes resources: Deployment, Service, Ingress  
- NGINX Ingress Controller for local DNS access  
- Secure storage of GitHub and DockerHub credentials  

Build Go app:
go build -o go-web

Run Docker image:
docker build -t <dockerhub-username>/go-web:v1 .
docker run -p 8080:8080 <dockerhub-username>/go-web:v1

Apply Kubernetes manifests:
kubectl apply -f k8s/manifests/

Accessing the App

App runs in Kubernetes cluster

Use NodePort or configure Ingress with local DNS:
http://go-web.local

