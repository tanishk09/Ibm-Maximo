# 🔑 What are AppPoints in IBM Maximo Application Suite (MAS)?  

**AppPoint** is the **common licensing unit** used across the **Maximo Application Suite (MAS)**.  
Instead of buying separate licenses for each MAS application (like Manage, Health, Monitor, Mobile, etc.), IBM introduced **AppPoints** so that customers purchase a single license pool and allocate it to the applications they want to use.  
This provides **flexibility and cost optimization**, since AppPoints can be reassigned or consumed by different MAS applications depending on user needs.  

---

## 📌 Key Highlights  

1. **AppPoint Licensing Model**  
   - Every MAS user is assigned AppPoints depending on which applications they access.  
   - Each MAS application has a defined AppPoint “cost” per user.  
   - AppPoints are **consumed dynamically** (when a user is provisioned in an application).  

2. **Advantages of AppPoints**  
   - Unified license across MAS applications.  
   - No need to purchase app-specific licenses.  
   - Flexibility to scale — add or move users between apps without buying new dedicated licenses.  
   - Better **license compliance tracking** via MAS licensing tools.  

---

## ⚙️ Example: AppPoint Consumption per User  

| Application       | AppPoints (per user) |
|-------------------|-----------------------|
| Maximo Manage     | 15                   |
| Maximo Mobile     | 5                    |
| Maximo Monitor    | 10                   |
| Maximo Health     | 20                   |
| Maximo Predict    | 25                   |

*(The above numbers can vary depending on IBM licensing agreements; this is just a representative example.)*  

---

## 🧮 Example Calculation  

Let’s assume an organization has purchased **1000 AppPoints**.  

- 20 users need **Manage** → 20 × 15 = 300  
- 10 users need **Mobile** → 10 × 5 = 50  
- 5 users need **Monitor** → 5 × 10 = 50  
- 3 users need **Health** → 3 × 20 = 60  

✅ Total Consumed = **460 AppPoints**  
➡️ Remaining Available = **540 AppPoints**  

This way, organizations can flexibly allocate the points as business needs evolve.  

---

## 📊 Visualization  

```mermaid
flowchart TD
    A[AppPoint License Pool] --> B[Maximo Manage Users - 15 pts]
    A --> C[Maximo Mobile Users - 5 pts]
    A --> D[Maximo Monitor Users - 10 pts]
    A --> E[Maximo Health Users - 20 pts]
    A --> F[Maximo Predict Users - 25 pts]
