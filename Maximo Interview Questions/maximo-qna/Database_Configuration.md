# IBM Maximo – Database Configuration Interview Q&A

This document contains common **interview questions and answers** related to **Database Configuration** in IBM Maximo.

---

### Q1. What is Database Configuration in Maximo?  
**Answer:**  
Database Configuration is a Maximo application used to define and manage the underlying customized backend database structure from the UI.  
You can create new objects, attributes, views, indexes, relationships, and more.

---

### Q2. What is the purpose of Apply Configuration Changes?  
**Answer:**  
It updates the physical database based on the changes made in Database Configuration.  
Without this step, the changes remain only at the application level and won’t take effect in the database.

---

### Q3. Why do we need to enable Admin Mode?  
**Answer:**  
Admin Mode is enabled to safely apply structural changes to the database (e.g., adding new fields, creating objects, or applying configuration changes).  
It ensures user activity does not interfere during this process.

---

### Q4. What happens to users when Admin Mode is ON?  
**Answer:**  
- Normal users cannot log in.  
- Cron tasks go into sleeping mode.  
- Reporting is disabled.  
- Only administrative users can access the system.  

---

### Q5. What is a persistent and non-persistent attribute?  
**Answer:**  
- **Persistent Attribute:** Stored permanently in the database.  
- **Non-Persistent Attribute:** Temporary; used in JVM memory only and not stored in the database.  

---

### Q6. What is the use of Relationships in DB Config?  
**Answer:**  
Relationships define how one object is linked to another (e.g., parent-child relationships).  
They are used in application linking and in binding fields for validation in **WHERE clause queries**.

---

### Q7. What is a View Object?  
**Answer:**  
A View Object is a logical object created from a database view, used to combine data from multiple tables.  
It allows applications to query across multiple sources as if they were a single object.  

---

### Q8. What is an Index in Maximo?  
**Answer:**  
An Index improves the performance of database queries.  
It allows faster searching, sorting, and filtering of records in large tables.

---

### Q9. What is the use of “Must Be” in Database Configuration?  
**Answer:**  
- If the **flag = 1**, the MaxType, Length, and Scale of the attribute cannot be changed.  
- If the **flag = 0**, those properties can be modified.  

---

### Q10. What is the difference between Structured and Non-Structured Data in Maximo?  
**Answer:**  
- **Structured Data:** Changes affect the actual database structure (tables, attributes). Requires **Admin Mode ON**.  
- **Non-Structured Data:** Changes affect only existing data values (not schema). Can often be applied live, without Admin Mode.  

---

### Q11. What is the role of “Same As Object” and “Same As Attribute” in Database Configuration?  
**Answer:**  
They indicate the **master attribute** from which an attribute inherits properties such as **MaxType, Length, and Scale**.  
This ensures data type consistency across objects.

---
