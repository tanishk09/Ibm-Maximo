# IBM Maximo - Asset Management Interview Q&A

## 1. What is the Asset Management Life Cycle in Maximo?
**Answer:**  
The **Asset Management Life Cycle** is the complete process of managing an asset from **planning, acquisition, operation, maintenance, and eventual disposal**.  
Maximo provides tools to track every stage, optimize asset performance, and control costs.

---

## 2. What is the difference between Linear and Non-Linear Assets in Maximo?
**Answer:**  
- **Linear Assets:** Assets that have a measurable length. Examples: Roads, Pipelines, Railroad tracks, Electric transmission lines.  
  - The Maximo Linear Add-on is used for such assets.  
  - Useful when defects need to be recorded, work performed, or meter readings taken at a measured point or span along the linear asset.  

- **Non-Linear Assets:** Assets that don’t have a defined length or path.  
  - Examples: Pumps, Machines, Motors.  
  - Tracked by their **location and characteristics** rather than a measurable span.

---

## 3. How does Maximo help in the Maintenance stage?
**Answer:**  
Maximo supports maintenance by:  
- Creating **Preventive Maintenance (PM)** schedules.  
- Automatically generating **Work Orders**.  
- Recording **maintenance history**.  
- Tracking **maintenance costs**.  
- Helping avoid unexpected breakdowns.

---

## 4. How are Assets linked with Locations in Maximo?
**Answer:**  
Each asset record in Maximo contains a **Location field** that shows where the asset is physically or logically placed.  
- When the asset moves, the location field is updated.  
- Work Orders linked to that asset automatically reflect the new location.

---

## 5. What is the difference between Asset Move and Asset Swap in Maximo?
**Answer:**  
- **Asset Move:** Changing the location of an asset from one place to another.  
- **Asset Swap:** Exchanging two assets between locations, updating both records simultaneously.

---

## 6. What is a Location in Maximo, and why is it important?
**Answer:**  
A **Location** in Maximo represents a physical or logical place where assets are kept or where work is performed.  

**Importance:**  
- Tracks **asset placement**.  
- Maintains **maintenance history**.  
- Provides **hierarchical reporting and analysis**.  

---

## 7. What is the purpose of Meters in Maximo Assets?
**Answer:**  
**Meters** track asset usage, condition, or performance values over time.  
They are used to:  
- Trigger **Preventive Maintenance (PM)**.  
- Support **Condition-Based Maintenance (CBM)** when thresholds are reached.  

---

## 8. What are Failure Codes in Maximo? Why are they important?
**Answer:**  
- **Failure Codes:** Predefined codes used to record the **problem, cause, and remedy** for asset or location failures.  
- **Importance:**  
  - Standardize failure reporting.  
  - Enable **root cause analysis**.  
  - Identify recurring issues.  
  - Support better **maintenance planning and preventive actions**.
