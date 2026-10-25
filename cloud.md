---
title: Cloud computing basics for Technical Writers
layout: default
---

# Cloud computing basics for Technical Writers
Most software you document today runs in the cloud, or connects to it. Whether you write API references, user guides, or release notes, you'll use cloud terms and explain cloud concepts to your readers. This article explains the fundamentals: what the cloud is, the types of clouds, the types of cloud services, the benefits, the use cases for each cloud model, and how cloud pricing works.

## What is the cloud?
Cloud computing is the delivery of computing services over the internet. These services include servers, storage, databases, networking, software, and analytics. Instead of buying and maintaining your own hardware, you use resources that a cloud provider hosts in its data centers.

Think of the cloud like electricity. You don't build a power plant to turn on a light. You use the power you need and pay for what you use. Cloud computing works the same way for computing resources.

## Key terms

| Term | Definition |
| --- | --- |
| Cloud provider | A company that offers cloud services, for example Google Cloud, Microsoft Azure, or Amazon Web Services (AWS). |
| Data center | A physical facility that houses servers, storage, and networking equipment. |
| Region | A geographic area that contains one or more data centers. |
| Virtualization | Technology that divides one physical server into multiple virtual machines. |
| Scalability | The ability to increase or decrease resources as demand changes. |
| Multitenancy | A model in which multiple customers share the same physical infrastructure, with their data kept separate. |

### Why Technical Writers need to know about the cloud
As a technical writer, you:
- Document products that are built on, deployed to, or integrated with cloud services.
- Use cloud-based tools for authoring, review, and publishing.
- Explain terms such as instance, region, and subscription accurately to customers.
- Need to describe the right deployment option to the right audience.

## Types of clouds
A cloud deployment model describes where the cloud infrastructure is located and who can use it. The three main models are public, private, and hybrid.

### Public cloud
A public cloud is owned and operated by a cloud provider. The provider makes computing resources available over the internet to anyone who wants to use or purchase them. Customers share the provider's infrastructure, but each customer's data and workloads remain isolated.

**Examples**: Google Cloud, Microsoft Azure, Amazon Web Services (AWS).

**Key characteristics**:
- The provider owns and maintains the hardware.
- You pay only for the resources you use.
- Resources are available on demand, and you can scale them quickly.

### Private cloud
A private cloud is used by a single organization. It can be located in the organization's own data center, or a third-party provider can host it. The infrastructure is dedicated to one customer and isn't shared with others.

**Examples**: A bank that runs its own virtualized environment in its on-premises data center by using VMware or OpenStack. A government agency that uses a dedicated, provider-hosted environment.

**Key characteristics**:
- The organization has full control over the infrastructure and security settings.
- The organization is often responsible for buying, maintaining, and updating the hardware.
- It costs more to set up than a public cloud.

### Hybrid cloud

A hybrid cloud combines a public cloud and a private cloud (or on-premises infrastructure). Data and applications can move between the two environments.
**Examples**: A retail company that keeps customer payment data in a private cloud, and runs its online store on a public cloud during holiday sales. A hospital that stores patient records on-premises and uses a public cloud for data analytics.

**Key characteristics**:
- You can keep sensitive workloads in a private environment.
- You can use the public cloud for extra capacity or less sensitive work.
- It's more complex to manage than a single environment.