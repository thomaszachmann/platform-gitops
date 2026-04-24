# platform-gitops

## Overview
GitOps repository defining the desired state of the platform across all environments (homelab and cloud).

This repository contains Kubernetes manifests, Helm releases, and ArgoCD application definitions used to declaratively manage and deploy platform services.

---

## Purpose
- Single source of truth for deployments
- Separation of CI (build) and CD (deploy)
- Declarative infrastructure and application management

Git defines what should run, ArgoCD ensures it actually runs.

---

## Structure
clusters/
  homelab/
  hetzner/

apps/
  vault/
  keycloak/
  harbor/

platform/
  monitoring/
  ingress/

---

## How it works
1. Changes are committed to this repository
2. ArgoCD continuously monitors the repository
3. Differences between desired and actual state are detected
4. ArgoCD automatically applies changes to the cluster

---

## Principles
- Declarative configuration
- Git as single source of truth
- Automated reconciliation
- Environment separation

---

## Important
This repository does NOT build or package applications.

It only defines what is running in the platform.