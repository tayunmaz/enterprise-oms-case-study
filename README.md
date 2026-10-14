# Enterprise Order Management System — Engineering Case Study

**Python · Flask · SQLAlchemy · MySQL · JavaScript · Docker · Microsoft Entra ID · EDI**

An engineering case study about work on an enterprise order management system (OMS) supporting furniture manufacturing operations—from order intake and inventory through production tracking, purchasing, and shipping.

> **Professional project, not a source-code release.** The original OMS was developed for an employer. This repository describes engineering concepts at a high level; it does not contain company source code, customer records, private configuration, or credentials. Confirm authorization before making this document public or adding employer-specific images or details.

## Project overview

Manufacturing operations depend on coordinated information across teams: orders affect material availability, purchasing demand, production, shipment planning, and logistics integrations. The OMS brings these workflows into a shared application.

| Layer | Technologies / scope |
| --- | --- |
| UI | Flask-rendered Jinja templates, JavaScript |
| Backend | Python, Flask, modular routes and services |
| Data | MySQL, SQLAlchemy |
| Authentication | Microsoft Entra ID integration, application roles |
| Real-time features | Flask-SocketIO, messaging infrastructure |
| Operations | Docker and environment-specific configuration |
| Integrations | EDI, third-party logistics and shipping documents |

## Conceptual architecture

```text
               Operations users (browser)
                         |
                  Flask / Jinja UI
                         |
            Authentication / Flask routes
                         |
                 Business services
              /           |          \
        Orders &       Inventory/     Shipping/
        production     purchasing     EDI
              \           |          /
                  SQLAlchemy ORM
                         |
                       MySQL

    External identity: Microsoft Entra ID
    External workflows: EDI and 3PL integrations
```

*This is a simplified conceptual diagram, not a production network topology.*

## Engineering work and challenges

### Order lifecycle and production tracking

The application supports operational visibility across manufacturing stages, including sewing, upholstery, wrapping, and shipping. Modeling transitions requires validation of business rules and consistent updates to related order records.

### Inventory and purchasing

Inventory and purchasing workflows connect materials and order demand with purchasing and receiving activities. Important concerns include relational modeling, quantity validation, and preventing inconsistent inventory updates.

### Enterprise identity and authorization

Microsoft Entra ID integration supports enterprise sign-in. Backend role and authorization checks govern access to operations; hiding UI actions is not a substitute for server-side enforcement.

### EDI and logistics integration

EDI workflows and third-party logistics integrations connect internal order data with external business processes. The system also supports logistics documents such as bills of lading (BOLs). Integration design must account for input validation, response handling, failures, and state tracking.

### Deployment and system organization

Flask routes, services, SQLAlchemy models, and Docker-based environments support a modular, testable application. Work in this area involves coordinating application configuration, persistence, and integration boundaries.

## Technical decisions worth discussing

| Challenge | Engineering consideration |
| --- | --- |
| Multi-stage manufacturing workflows | Validate transitions on the backend and keep workflow state consistent |
| Relational business data | Design relationships among orders, materials, purchasing, and shipping entities |
| Enterprise authentication | Map external identities to local application roles and permissions |
| Business integrations | Keep outbound effects and errors visible and traceable |
| Safe demonstrations | Use fictional data and isolate the demo from company infrastructure |

These are system-level descriptions. Individual ownership, quantified improvements, and production outcomes should be added only when accurately supported and approved for publication.

## Demo and source-code availability

A separate local portfolio showcase was prepared using fictional data and read-only guest navigation for dashboards, orders, inventory, production, purchasing, shipping, and EDI. It is **not publicly hosted**, and its source code is **not included here**.

This case study is designed for recruiters and engineering interviewers who want to understand the domain, architecture, and technical challenges without exposing proprietary employer material.

## Skills illustrated

Python · Flask · SQLAlchemy · MySQL · JavaScript · REST APIs · Authentication and authorization · EDI · Logistics workflows · Docker · Backend validation

---

**Related independent project:** [Q'd — full-stack mobile application](https://github.com/tayunmaz/qd) (currently private).

*This case study does not claim sole authorship of the employer's application.*
