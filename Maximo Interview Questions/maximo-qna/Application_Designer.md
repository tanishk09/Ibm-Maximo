# IBM Maximo - Application Designer Interview Q&A

## 1. What is an Application Designer in Maximo?
**Answer:**  
**Application Designer** is a Maximo configuration tool that allows you to **customize the UI layout** of applications (like Work Order Tracking, Asset, etc.) without modifying core code.  

With Application Designer, you can:  
- Add / Remove / Change fields.  
- Configure dialogs, lookups, action menus, tabs, labels, rows, sections, and buttons.  
- Apply **conditional UI behavior**.  

---

## 2. How many types of applications can be created in Application Designer?
**Answer:**  
There are **three types of applications** created in Application Designer:  
1. **Power App**  
2. **Self Service**  
3. **Single Page**  

---

## 3. What is the difference between Power App and Self Service?
**Answer:**  
- **Power App:**  
  - Standard, full-featured classic type of applications.  
  - Provide complete functionality, multiple tabs, dialogs, sections, action menus, and toolbar buttons.  

- **Self Service App:**  
  - Simplified, user-friendly applications for casual users.  
  - Typically used by end users (e.g., to raise Service Requests).  

---

## 4. How many types of XML have you worked on in Application Designer?
**Answer:**  
Worked on the following XML types:  
- **Application XML**  
- **Dialog XML**  
- **Library XML**  
- **Lookup XML**  
- **Presentation XML**  

---

## 5. Can we add custom fields in Maximo using Application Designer?
**Answer:**  
No. Application Designer is only used to **display existing database fields**.  
To add a new field:  
1. First use **Database Configuration** to add the field.  
2. Then use **Application Designer** to place the new field on the UI.

---

## 6. Scenario: You added a new field in Database Config but it’s not visible in the application. What will you do?
**Answer:**  
1. Apply **DB changes** and restart Maximo if required.  
2. Open **Application Designer**.  
3. Select the application (e.g., `ASSET`).  
4. Use the **Control Palette** → Drag a **Textbox** to the desired section.  
5. Set the **attribute** to the newly added field.  
6. Save changes.  

---

## 7. How can you add a custom table in a tab in the Work Order Tracking application?
**Answer:**  
1. Create a **relationship** between `WORKORDER` and your custom object in **Database Configuration**.  
2. Open **Application Designer** and select the `WOTRACK` application.  
3. Add a **new tab**.  
4. From the **Control Palette**, drag a **Table** into the new tab.  
5. Set the **Data Source** of the table to the newly created relationship.  

---

## 8. Can you directly edit Application Designer XML?
**Answer:**  
Yes.  
- Use the **Export XML** feature in Application Designer.  
- Modify the layout or controls as needed.  
- Import the updated XML back.  
⚠️ Always take a **backup** before importing.  

---

## 9. What are some common XML tags in Application Designer?
**Answer:**  
Some common XML tags used in Application Designer include:  
- `<textbox>`  
- `<table>`  
- `<section>`  
- `<tab>`  
- `<dialog>`  
