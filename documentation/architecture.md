# Enterprise Network Architecture

## 1. Architecture Overview

This document provides a technical overview of a sanitized enterprise network architecture.

The architecture follows a hierarchical design consisting of Internet/WAN connectivity, a security and edge layer, core switching, distribution infrastructure, user and wireless access, data center services, and disaster recovery infrastructure.

The design emphasizes resiliency, high availability, network hierarchy, infrastructure segmentation, and service continuity.

---

## 2. Internet / WAN

The architecture uses multiple upstream Internet Service Providers (ISPs) to provide external network connectivity.

Dual ISP connectivity improves network resiliency by reducing dependency on a single external connection.

---

## 3. Security / Edge

The security and edge layer provides the primary security boundary between external networks and the internal enterprise environment.

A high-availability firewall design is used to provide redundancy at the network perimeter and improve service continuity in the event of a firewall failure.

Perimeter switching provides connectivity between the upstream ISP connections and the security infrastructure.

---

## 4. Core Network

The core layer provides centralized, high-speed connectivity between the security perimeter, distribution infrastructure, and data center environments.

A core switch stack is used to provide a resilient logical switching platform and simplify management of the core network.

---

## 5. Distribution Layer

The distribution layer provides connectivity between the core network and downstream infrastructure.

This layer connects user access, wireless infrastructure, and data center environments to the core network.

The distribution architecture also provides logical separation between different infrastructure roles and network segments.

---

## 6. User and Wireless Access

The access portion of the architecture provides connectivity for end users and wireless infrastructure.

User and wireless connectivity is separated from core and data center infrastructure to support network segmentation and security policy enforcement.

---

## 7. Data Center

The data center environment provides infrastructure services for enterprise workloads.

The architecture includes dedicated distribution connectivity for data center infrastructure, with virtualization and shared storage providing the underlying platform for hosted workloads.

---

## 8. Disaster Recovery

A dedicated disaster recovery environment is represented within the architecture.

The DR environment includes separate distribution, virtualization, and storage infrastructure to support service continuity and recovery objectives.

The separation between primary and disaster recovery infrastructure reduces dependency on a single infrastructure environment.

---

## 9. Virtualization and Storage

Virtualization infrastructure provides the compute platform for hosted enterprise workloads.

Shared storage provides centralized storage resources for the virtualization environment.

The architecture also represents corresponding virtualization and storage infrastructure within the disaster recovery environment.

---

## 10. High Availability and Resiliency

Several architectural components are designed with resiliency in mind:

- Dual ISP connectivity
- Firewall high availability
- Core switch stacking
- Separate primary and disaster recovery environments
- Redundant infrastructure paths

These mechanisms reduce single points of failure and improve overall infrastructure availability.

---

## 11. Design Principles

The architecture demonstrates the following design principles:

- Hierarchical network architecture
- High availability
- Redundancy
- Network segmentation
- Separation of infrastructure roles
- Centralized core connectivity
- Data center isolation
- Disaster recovery
- Service continuity

---

## Disclaimer

This documentation describes a sanitized and generalized enterprise network architecture for educational and portfolio purposes.

No production credentials, IP addresses, hostnames, configuration files, secrets, or other confidential operational information are included.
