# IBM Maximo Domains - Interview Q&A

This document contains important interview questions and answers related to **Domains in IBM Maximo**.  
It is designed for quick preparation and knowledge sharing.

---

### Interviewer:
What is a Domain in Maximo? Explain with an example.

### Candidate:
A domain in Maximo is a predefined set of lookup values that can be used in fields (attributes). It controls the dropdown values list for user selection.  
**Example:** For the Priority field in Work Order, if we want only LOW, MEDIUM, and HIGH as options, we define an ALN Domain and associate it with the field.

---

### Interviewer:
How many types of Domains are there in Maximo?

### Candidate:
There are six types of domains in Maximo:
1. ALN Domain  
2. NUMERIC Domain  
3. NUMERIC RANGE Domain  
4. CROSSOVER Domain  
5. TABLE Domain  
6. SYNONYM Domain  

---

### Interviewer:
What is the difference between Table Domain and Crossover Domain in Maximo?

### Candidate:
- **Table Domain**: A dynamic lookup used to display a dropdown list of values, fetching data from another table.  
  *Example:* To show a list of employees for selection, a Table Domain can fetch data from the PERSON table.  
- **Crossover Domain**: Used to auto-copy field data from one object to another.  
  *Example:* When you select an asset in a work order, its location gets filled automatically.

---

### Interviewer:
Can you create your own custom domain? Where can you assign a domain to an attribute in Maximo?

### Candidate:
Yes, we can create a custom domain.  
1. Go to the **Domains application** in Maximo.  
2. Choose a domain type (e.g., ALN).  
3. Click *New Row*, create the ALN domain, choose data type, and add values.  
4. Save.  
Then, go to **Database Configuration**, select the object and attribute, and enter your domain name in the domain field.

---

### Interviewer:
Can you filter values in a Table Domain using conditions?

### Candidate:
Yes, by using the **List Where Clause**.  
**Example:** `status = 'ACTIVE'` will only display active values in the dropdown.

---

### Interviewer:
Can a Crossover Domain copy multiple fields at once?

### Candidate:
Yes, a single crossover domain can map multiple source fields to multiple target fields.

---

### Interviewer:
What is a Synonym Domain? Where is it used?

### Candidate:
- **Synonym Domains** are special domains reserved by the system.  
- Their internal values are used by the business logic of Maximo.  
- You cannot add new internal values, but you can add synonyms to internal values for user display.  

**Example:**  
Work Order Status is a synonym domain.  
Internal values include:  
- `WAPPR` (Waiting on Approval)  
- `APPR` (Approved)  
- `COMP` (Completed)  

---

### Interviewer:
What happens if you delete a domain that is in use?

### Candidate:
You cannot delete a domain that is currently in use.  
Maximo will throw an error saying the domain is referenced.

---
