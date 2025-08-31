# Maximo Automation Script Interview Questions & Answers

This document contains commonly asked interview questions and answers related to **Automation Scripts in IBM Maximo**.

---

### **Q1. What is an Automation Script in Maximo?**
**A:** An automation script in Maximo is a way to implement business logic using scripting languages like Jython, Python, or JavaScript without customizing Java code. It allows you to manipulate MBOs, perform validations, default values, and integrate with publish channels and enterprise services.

---

### **Q2. What are the types of Launch Points in Automation Script?**
**A:** There are six main types of launch points:
1. Script with No Launch Point  
2. Object Launch Point  
3. Attribute Launch Point  
4. Action Launch Point  
5. Script for Integration  
6. Custom Condition Launch Point  

---

### **Q3. Difference between Object and Attribute Launch Point?**
**A:**  
- **Object Launch Point** → Triggers on actions at the record level (e.g., add, before save, after save).  
- **Attribute Launch Point** → Triggers on specific field-level events (e.g., validate, run action, initialize value, retrieve list).  

---

### **Q4. What is the difference between MBO and MBOSet?**
**A:**  
- **MBO** → A single record (like one WORKORDER).  
- **MBOSet** → A collection of MBOs (like a list of WORKORDERs).  

---

### **Q5. Can you access the owner MBO from a child MBO?**
**A:** Yes. You can access the parent record using the `mbo.getOwner()` method.  
```python
parentMbo = mbo.getOwner()
```

---

### **Q6. How do you get and set field values in a script?**
**A:**  
- To get a value:  
```python
status = mbo.getString("STATUS")
```  
- To set a value:  
```python
mbo.setValue("STATUS", "INPRG")
```

---

### **Q7. Why is the use of mbo.getMboSet()?**
**A:** `mbo.getMboSet("RELATIONSHIP")` is used to return a related record set (child MBOSet) from the current record using a defined relationship (e.g., TASKS from WORKORDER or WPMATERIAL).

---

### **Q8. What is MboConstants and when do you use it?**
**A:** `MboConstants` provides constants like `MboConstants.NOACCESSCHECK`, which are used to bypass access restrictions when setting field values.  
Example:  
```python
mbo.setValue("STATUS", "APPR", MboConstants.NOACCESSCHECK)
```

---

### **Q9. What is a Zombie MBO?**
**A:** A Zombie MBO occurs when an MBO has been used but later deleted, closed (closing an MboSet), or its data is removed from the session. If you try to access it again, it no longer has a valid reference in the database.  
It exists in the MBO system but behaves like a "dead" object, hence called a **Zombie MBO**.

---
