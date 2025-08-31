# IBM Maximo - Inventory Management Interview Q&A

## 1. What is Inventory Management?
**Answer:**  
**Inventory Management** manages all the spare parts, consumables, and materials that are stored in storerooms. It helps organizations by:  
- Tracking stock levels (how many items are available).  
- Managing storerooms and locations.  
- Issuing and returning items to Work Orders.  
- Reordering items when stock is low.

---

## 2. What is the Item Master? What are its main uses?
**Answer:**  
The **Item Master** is the application where all items are first created and defined. It acts like a catalog or library of items which can later be added into storerooms.  

**Main uses of Item Master:**  
- Create and define items (name, description, unit of measure, part number, lot/not-lot, commodity codes/groups, etc.).  
- Mark items as **rotating (repairable)** or **non-rotating (consumable)**.  
- Control whether an item is stocked in Inventory or used directly.  
- Attach vendor information for purchasing.  
- Set condition codes, warranty details, and specifications.

---

## 3. What is the difference between Rotating and Non-Rotating Items?
**Answer:**  
- **Rotating Item:** An item that can be repaired and reused.  
  *Example: Motor, Pump, Gearbox*  
- **Non-Rotating Item:** A consumable item that cannot be reused.  
  *Example: Grease, Oil, Bolt, Nut*  

---

## 4. What is Reorder in Maximo?
**Answer:**  
**Reorder** in Maximo is the process of automatically creating **Purchase Requisitions (PRs)** or **Purchase Orders (POs)** when inventory stock falls below the minimum balance.

---

## 5. What are the methods of Reordering in Maximo?
**Answer:**  
There are three main methods of Reordering in Maximo:  
1. **Reorder Point:** Orders items when stock reaches the minimum balance.  
2. **Economic Order Quantity (EOQ):** Orders based on demand and economic order calculations.  
3. **Lead Time (Days):** Orders items based on the number of days needed for replenishment.

---

## 6. What are the differences between LOT items and NOT-LOT items?
**Answer:**  
- **LOT Items:** Stock is managed **batch-wise**. Each batch has its own **Lot Number, Expiry Date, Manufacture Date, and Specifications**.  
  *Example: Medicines, Chemicals, Paints, Food items.*  
- **NOT-LOT Items:** Stock is not managed batch-wise. Only the total quantity is tracked, and expiry details are not required.  
  *Example: Bolts, Nuts, Wires, Bearings.*

---

## 7. What is the difference between Soft, Hard, and Backorder Reservations?
**Answer:**  
- **Soft Reservation:** The system reserves the item logically but does not lock the stock. The item is still available for other Work Orders until actually issued.  
- **Hard Reservation:** The system reserves the item physically and locks the quantity. That stock cannot be used for any other Work Order.  
- **Backorder Reservation:** Created when the item stock is not available. The system places a reservation in **backorder mode** until stock is replenished.
