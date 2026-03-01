---
title: "OpenShift Platform in Hybrid Operation Model"
# s GitOps: Automatizované nasazování aplikací"
date: 2024-07-25
author: "Cloud4You"
description: "Most organizations today face growing demands for flexibility and performance of IT infrastructure. The hybrid operation model of the OpenShift platform, where worker nodes are deployed both on virtual servers and physical servers (bare metal), represents an effective solution. This model allows combining the benefits of both environments: the flexibility and easy management of virtual machines together with the high performance and efficiency of bare metal servers."
categories: ["containers"]
tags: ["cloud", "kubernetes", "redhat", "openshift"]
featured_image: "/images/blog/ocp.jpg"   #w:h 1,9:1
---

<!-- {{< toc >}} -->

## Introduction

Most organizations today face growing demands for flexibility and performance of IT infrastructure. The hybrid operation model of the OpenShift platform, where worker nodes are deployed both on virtual servers and physical servers (bare metal), represents an effective solution. This model allows combining the benefits of both environments: the flexibility and easy management of virtual machines together with the high performance and efficiency of bare metal servers.

## Goals and Benefits of the Hybrid Model

### Key Goals

* Optimization of infrastructure operating costs.
* Ensuring performance for demanding workloads (AI/ML) while maintaining flexible cluster scaling.
* Flexibility in deploying and scaling workloads.
* Easier extensibility and compatibility with existing IT systems.

### Benefits of the Hybrid Model

* __Performance:__ Bare metal workers provide better performance for applications that need direct access to hardware.
* __Scalability:__ Virtual machines allow quick response to changes in computational capacity requirements.
* __Cost Optimization:__ Possibility to combine more expensive but高性能 bare metal workers equipped with powerful graphics cards with more flexible scaling of the entire cluster using virtual workers.

## Hybrid OpenShift Cluster Architecture

### Cluster Structure

* __Control plane:__ Runs on virtual servers for easy management and redundancy.
* __Worker nodes:__
  * __Virtual servers:__ Intended for standard workloads and microservices applications.
  * __Bare metal servers:__ Used for applications with high performance requirements.

### Integration with Existing Infrastructure

* Connection with existing virtualization platform (VMware).
* Cluster provisioning automation using Infrastructure-as-Code (Ansible).

## Implementation and Operation

### Hybrid Cluster Deployment

* __Planning:__ Definition of workloads and decision on which applications will run on which nodes.
* __OpenShift Installation:__ Using the OpenShift Installer and deployment according to our proposal, which is fully automated.
* __Configuration:__
  * Setting conditions for workload scheduling (node affinity, tolerations).
  * Optimization of network communication between virtual and bare metal workers.
* __Monitoring and observability:__
  * Using Prometheus, Grafana and OpenTelemetry for monitoring performance and cluster status.
  * Log management using OpenShift Logging stack with ECK Cloud deployed in on-premise environment.

## Conclusion

The hybrid operation model of OpenShift combines the flexibility and cost efficiency of virtual servers with the high performance of bare metal workers. This approach provides an ideal solution for demanding workloads that need a scalable and efficient platform for modern applications using AI/ML.
