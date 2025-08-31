# IBM Maximo Application Suite (MAS) - Setup Types

This document explains the different **MAS Setup Types**, their **use cases**, **infrastructure requirements**, and **suitability** for different organizations.

---

## 1. Local (Standalone)
- **Platform:** Red Hat OpenShift Local (Single Node OpenShift)  
- **Use Case:** POC, Demo, Learning, Development  
- **Infra Needed:** Laptop with OpenShift Local  
- **Suitable For:** Developers, Trainers  

---

## 2. On-Premise (Multi-node)
- **Platform:** Your own physical or virtual infrastructure, RHOSP (Red Hat OpenStack Platform), or OpenShift Cluster on bare-metal  
- **Features:** High Availability, Monitoring, Logging, Enterprise Control  
- **Use Case:** Production, Staging  
- **Infra Needed:** Your own hardware  
- **Suitable For:** Enterprises  

---

## 3. Private Cloud
- **Platform:** OpenShift cluster on virtualization platforms like VMWare, Nutanix  
- **Deployment:** MAS installed via OpenShift Operator & Catalog  
- **Use Case:** Enterprise Production  
- **Infra Needed:** Virtual Infra (e.g., VMware, Nutanix)  
- **Suitable For:** Corporates  

---

## 4. Public Cloud
- **Platform:** OpenShift Cluster in AWS, Azure, IBM Cloud  
  - ROSA (Red Hat OpenShift Service on AWS)  
  - ARO (Azure Red Hat OpenShift)  
- **Use Case:** Scalable Cloud Production  
- **Infra Needed:** AWS, Azure, IBM Cloud  
- **Suitable For:** Cloud-friendly Organizations  

---

## 5. IBM Hosted MAS SaaS
- **Platform:** IBM Hosted MAS (SaaS Model)  
- **Management:** Fully managed by IBM (no manual OpenShift setup)  
- **Use Case:** Fully Managed by IBM  
- **Infra Needed:** No infra required by client  
- **Suitable For:** Customers who want **zero infrastructure management**  

---
