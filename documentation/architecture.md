# Enterprise Network Architecture

## 1. Architecture Overview

This document provides a technical overview of a sanitized enterprise network architecture.

The architecture follows a hierarchical design consisting of Internet/WAN connectivity, a security and edge layer, a centralized Layer 3 core, downstream distribution infrastructure, data center services, virtualization, enterprise storage, and a physically and logically separated disaster recovery environment.

The design emphasizes:

- High availability
- Network resiliency
- Centralized Layer 3 routing
- Functional separation of network infrastructure
- Data center service continuity
- Disaster recovery capability
- Scalable enterprise connectivity

---

## 2. Architecture Goals

The architecture is designed around the following objectives:

- Provide resilient external network connectivity through multiple Internet Service Providers
- Maintain service continuity through firewall high availability
- Provide a centralized and resilient network backbone
- Centralize Layer 3 gateway and inter-VLAN routing functions
- Separate user, wireless, data center, and disaster recovery connectivity
- Support enterprise virtualization and storage infrastructure
- Provide a physically and logically separated disaster recovery environment
- Minimize unnecessary dependency between downstream network segments
- Provide a scalable foundation for future infrastructure expansion

---

## 3. Internet / WAN

The enterprise environment uses two independent Internet Service Provider connections.

The connections are both operationally active and serve different primary traffic roles.

### ISP 1

ISP 1 primarily provides Internet connectivity for enterprise client and user traffic.

This connection is mainly associated with general user Internet access.

### ISP 2

ISP 2 primarily supports server-related connectivity, public-facing services, and Operational Technology (OT) network connectivity.

The separation of traffic roles between the two upstream connections provides greater control over traffic flows and reduces dependency on a single Internet connection for all enterprise services.

Detailed routing policies, public IP addressing, and traffic engineering configurations are intentionally excluded from this public documentation.

---

## 4. Security / Edge Layer

The security and edge layer forms the primary boundary between external networks and the internal enterprise environment.

The architecture includes:

- Dual perimeter switching infrastructure
- A high-availability firewall pair
- Connectivity between the external ISP connections and the internal core network

### Firewall High Availability

The firewall infrastructure operates as a high-availability pair.

One firewall operates in the active role while the second firewall remains in standby and is capable of taking over in the event of an active firewall failure.

This design improves service continuity and reduces the risk of a single firewall becoming a single point of failure.

Detailed firewall policies, security rules, authentication information, and configuration parameters are intentionally omitted.

---

## 5. Core Network

The core layer serves as the backbone of the enterprise network.

It provides high-speed connectivity between:

- The security and edge layer
- User distribution infrastructure
- Wireless infrastructure
- Data center infrastructure
- Disaster recovery infrastructure

The core also provides the primary Layer 3 routing function for the enterprise environment.

### Layer 3 Gateway

Multiple Switch Virtual Interfaces (SVIs) are hosted on the core infrastructure.

These SVIs provide the default gateways for downstream network segments and enable centralized inter-VLAN routing.

This design establishes a centralized Layer 3 boundary at the core while keeping downstream distribution infrastructure focused primarily on connectivity and access functions.

---

## 6. Distribution Layer

The distribution layer provides downstream connectivity between the core network and user, wireless, and data center environments.

The distribution switches do not provide default gateway functionality. Their Layer 3 configuration is primarily used for management purposes, while gateway and inter-VLAN routing functions remain centralized at the core.

### Wired User Connectivity

Selected distribution switches primarily provide wired network connectivity for enterprise users.

These switches support connectivity for employees working in dedicated office spaces, work areas, and designated network access locations.

### Wireless Connectivity

Other distribution switches primarily provide connectivity for wireless access infrastructure.

This includes wireless connectivity used by enterprise users and guest network services.

The functional separation of distribution infrastructure allows different access environments to be organized while maintaining centralized Layer 3 routing at the core.

---

## 7. Data Center

The data center environment is connected through dedicated distribution infrastructure.

The data center network provides connectivity for enterprise computing and infrastructure services, including:

- Virtualization infrastructure
- Oracle server infrastructure
- Enterprise storage
- Supporting data center services

The data center distribution layer provides downstream connectivity to these infrastructure systems while relying on the core for centralized network gateway and routing functions.

---

## 8. Virtualization Infrastructure

The primary data center contains a VMware-based virtualization environment.

The virtualization cluster provides the computing platform for virtualized enterprise workloads and infrastructure services.

The virtualization environment is connected to the data center network and supported by enterprise storage infrastructure.

The architecture separates the virtualization layer from the network and storage layers, allowing each infrastructure component to be managed and scaled independently.

---

## 9. Enterprise Storage

The primary virtualization environment is supported by dedicated enterprise storage infrastructure.

The storage layer provides shared storage resources for the virtualization environment and enables centralized management of virtual machine storage.

The storage infrastructure is represented separately from the virtualization cluster to illustrate the logical separation between compute and storage resources.

Specific storage models, configurations, capacity information, and operational parameters are intentionally omitted.

---

## 10. Disaster Recovery

The architecture includes a dedicated disaster recovery environment that is physically and logically separated from the primary data center.

The disaster recovery environment contains corresponding infrastructure components, including:

- DR distribution infrastructure
- DR virtualization infrastructure
- DR storage infrastructure

The separation of the primary and disaster recovery environments reduces the risk of a single site-level failure affecting both environments.

The DR architecture is intended to support infrastructure recovery and service continuity in the event that the primary environment becomes unavailable.

Specific recovery procedures, replication configurations, recovery objectives, addressing information, and operational details are intentionally excluded.

---

## 11. High Availability and Resiliency

High availability and resiliency are incorporated at multiple architectural layers.

### Internet Connectivity

Two active ISP connections provide independent external connectivity paths with different primary traffic roles.

### Firewall

A high-availability firewall pair provides redundancy at the network security boundary.

### Core Network

The core infrastructure provides a centralized and resilient backbone for downstream network segments.

### Data Center

The data center infrastructure is separated into dedicated network, compute, and storage components.

### Disaster Recovery

A physically and logically separated DR environment provides an additional layer of protection against site-level infrastructure failures.

Together, these mechanisms reduce single points of failure and improve overall infrastructure resilience.

---

## 12. Design Principles

The architecture follows several fundamental enterprise infrastructure design principles:

### Centralized Layer 3 Routing

Layer 3 gateway and inter-VLAN routing functions are centralized at the core to provide a consistent routing boundary.

### Hierarchical Network Design

The network follows a hierarchical structure consisting of edge, core, distribution, and downstream infrastructure layers.

### Functional Separation

User, wireless, data center, and disaster recovery infrastructure are organized according to their operational roles.

### High Availability

Critical infrastructure components are designed with redundancy where appropriate to improve service continuity.

### Infrastructure Isolation

The disaster recovery environment is physically and logically separated from the primary environment to reduce the impact of site-level failures.

### Scalability

The architecture provides a structured foundation that allows additional network segments, infrastructure services, and downstream connectivity to be introduced without fundamentally changing the overall design.

---

## 13. Security Considerations

This repository contains a sanitized representation of an enterprise infrastructure environment.

The following information has been intentionally removed or generalized:

- IP addresses and subnet information
- VLAN identifiers
- Device hostnames
- Management addresses
- Firewall policies and security rules
- Routing configuration
- Authentication information
- Credentials and secrets
- Public-facing service details
- Vendor-specific operational configuration
- Infrastructure location details

The purpose of this repository is to demonstrate architecture design and documentation practices without exposing operational infrastructure information.

---

## 14. Disclaimer

This architecture is a sanitized and generalized representation of an enterprise IT environment.

The topology, terminology, component roles, and architectural relationships have been modified where necessary for public documentation.

No confidential credentials, operational configuration, sensitive addressing information, or security policies are included in this repository.
