# IBM Maximo - Purchasing Module Interview Q&A

## 1. What is the Purchasing Module in Maximo?
**Answer:**  
The **Purchasing Module** manages the end-to-end procurement process including purchase requisitions, RFQ, purchase orders, receiving, and invoices. It covers everything from requesting items, creating POs, tracking approvals, receiving items, to invoicing and payment.

---

## 2. What is the difference between Purchase Requisition (PR) and Purchase Order (PO)?
**Answer:**  
- **Purchase Requisition (PR):** An internal request raised by a department or user to purchase a needed item or service.  
- **Purchase Order (PO):** A document detailing the items, quantities, prices, and delivery terms issued to a vendor to supply items/services.

---

## 3. How does Purchasing link with Work Orders?
**Answer:**  
Direct Issue POs can be linked to **Work Orders** so that received items are directly consumed by that WO.

---

## 4. How do you handle partial receiving in Maximo?
**Answer:**  
Maximo allows **partial receiving** of items. The PO remains open until all items are fully received at the inventory level.

---

## 5. What happens if a PO is revised in Maximo?
**Answer:**  
A **Revised PO** is a new version of an existing PO, created to allow modifications (e.g., adding item lines, changing costs).  
- Once approved, the prior version is marked as **Revised** and becomes a read-only history record.  
- The new version is set to **PNDREV** and awaits final approval.

---

## 6. What is a Conversion Factor in Maximo?
**Answer:**  
A **Conversion Factor** is used to convert one unit of measure (UOM) into another, maintaining consistency between Purchasing UOM and Inventory UOM.  

**Example:**  
- You store bolts in boxes but issue them in pieces.  
- 1 Box = 50 Pieces.  
- Conversion Factor = 50.  
- Purchasing 2 Boxes = 100 Pieces in Inventory.

---

## 7. What is RFQ in Maximo?
**Answer:**  
**RFQ (Request for Quotation):** A process where an organization invites multiple vendors to provide price quotations for goods or services before finalizing a Purchase Order.

---

## 8. What is GRN in Maximo? Why is it important?
**Answer:**  
- **GRN (Goods Receipt Note):** A document generated when goods/services are received against a PO in Maximo.  
- **Importance:**  
  - Updates inventory stock levels.  
  - Ensures proof of delivery.  
  - Enables invoice matching for payment.

---

## 9. What is the role of Inspection in a PO?
**Answer:**  
The **Inspection** in a PO is used to verify the quality and correctness of items/services received from a vendor before they are accepted into inventory.

---

## 10. What are possible results of Inspection?
**Answer:**  
- **Accepted:** Goods are correct and added to inventory/work order.  
- **Rejected:** Goods are wrong/damaged and returned to vendor.
