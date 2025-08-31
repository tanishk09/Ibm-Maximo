# IBM Maximo - Work Order Management Interview Q&A

## 1. What is the Work Order life cycle in Maximo?
**Answer:**  
The **Work Order life cycle** is the sequence of statuses a work order passes through from creation to closure. It typically includes:  
- **Initiation** (often from a Service Request)  
- **Planning** (defining tasks, materials, labor)  
- **Approval**  
- **Scheduling / PM**  
- **Execution**  
- **Completion / Closure**

---

## 2. What happens if materials are not available for a Work Order?
**Answer:**  
The Work Order can move to the status **WMATL (Waiting for Materials)** until the required materials are issued from Inventory.

---

## 3. What is Direct Issue in Maximo?
**Answer:**  
**Direct Issue** means issuing materials directly to a Work Order or Asset without storing them in Inventory.  
- Normally, purchased items go into Inventory (Storeroom) first and then are issued to a Work Order.  
- For rarely used or expensive items, it doesn’t make sense to stock them.  
- In such cases, a **Purchase Requisition (PR)** or **Purchase Order (PO)** is created with a **Direct Issue flag**, and the item is delivered straight to the Work Order.

---

## 4. What is the difference between a Stocked item and a Direct Issue item?
**Answer:**  
- **Stocked Item:** Stored in Inventory first, then issued to Work Orders as needed.  
- **Direct Issue Item:** Purchased and issued directly to a Work Order without storing in Inventory.

---

## 5. What is the difference between Originator and Follow-up in a Work Order?
**Answer:**  
- **Originator:** The original Work Order or Ticket from which a new record is created. It serves as the initial request or identification.  
- **Follow-up:** A new Work Order or Ticket created from an existing Originator record. It’s used when additional work is needed on the same Asset or Location.  

---

## 6. What is a Worklog in Maximo Work Order?
**Answer:**  
A **Worklog** is a note or communication record attached to a Work Order. It captures updates, technician notes, troubleshooting steps, or communication history for tracking and audit purposes.

---

## 7. What are the types of Worklogs in Maximo?
**Answer:**  
There are two types of Worklogs in Maximo:  
1. **Communication Log:** Records emails, notifications, or system-generated messages.  
2. **Work Log:** Records technician notes, actions taken, or work progress.

---

## 8. Why is the Actuals tab important in a Work Order?
**Answer:**  
The **Actuals tab** is used to record the actual labor, materials, services, and tools consumed during the execution of a Work Order.  
- Helps track the **real cost vs. planned cost**.  
- Provides better cost visibility and reporting.
