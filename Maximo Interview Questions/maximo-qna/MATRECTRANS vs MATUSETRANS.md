# Maximo Interview Q&A – Inventory Transactions (MATRECTRANS vs MATUSETRANS)

---

## Question 1: Can you explain the difference between MATRECTRANS and MATUSETRANS tables in Maximo?

**Answer:**

- **MATRECTRANS (Material Receipt Transactions)**  
  - Used to track material receipts into the system.  
  - Stores records whenever material is **received into inventory**, whether via:  
    - Purchase Order (PO) receipt  
    - Transfer Order receipt  
    - Vendor return  
  - Example: When a PO is received in a storeroom, a record is created in MATRECTRANS.  
  - **Key Fields**: `PONUM`, `ITEMNUM`, `QTY`, `LOCATION`, `RECEIPTDATE`.

---

- **MATUSETRANS (Material Usage Transactions)**  
  - Used to track material usage and issues.  
  - Stores records whenever material is **issued out of inventory**, such as:  
    - Issuing to a Work Order (WO)  
    - Direct issue to a department  
    - Returning unused material back to inventory  
  - Example: When a technician takes material for a WO, MATUSETRANS logs the transaction.  
  - **Key Fields**: `WONUM`, `ITEMNUM`, `QTY`, `FROMSTORELOC`.

---

## Question 2: Why do we need both MATRECTRANS and MATUSETRANS in Maximo? Can’t we manage with just one transaction table?

**Answer:**

We need both because they capture **two different aspects** of the inventory lifecycle:

- **MATRECTRANS → Incoming transactions**  
  - Captures **inventory inflow** (goods received into the storeroom).  
  - Ensures stock availability updates, receipt auditing, and supplier accountability.  

- **MATUSETRANS → Outgoing transactions**  
  - Captures **inventory outflow** (goods issued/consumed).  
  - Tracks material usage, cost allocation, stock planning, and accountability for consumption.  

👉 Having **two separate tables** provides a **clear separation** of inbound vs. outbound material movements, ensures accurate reporting, and supports audit/compliance requirements.

---
