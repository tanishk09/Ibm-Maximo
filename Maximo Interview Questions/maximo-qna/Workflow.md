# IBM Maximo - Workflow Application Interview Q&A

## 1. What is the Workflow in Maximo?
**Answer:**  
A **Workflow** in Maximo is a tool used to **automate business processes** such as Work Order approvals, Service Request routing, Purchase Requisitions, etc.  
It ensures that tasks follow a **defined path from start to completion**.

---

## 2. What are the main components of a Maximo Workflow?
**Answer:**  
The main components of a Workflow are known as **Nodes**. There are **8 types of nodes**:  
1. **Start Node**  
2. **Task Node**  
3. **Condition Node**  
4. **Interaction Node**  
5. **Manual Input Node**  
6. **Wait Node**  
7. **Subprocess Node**  
8. **Stop Node**

---

## 3. What is the difference between Interaction Node and Subprocess Node?
**Answer:**  
- **Interaction Node:** Used when user input is required.  
  - Sends a task to the user’s Workflow Inbox asking for actions such as *Approve, Reject, or Route*.  

- **Subprocess Node:** Used when another workflow needs to be reused within the current workflow.  
  - Runs in the background and does **not require user interaction**.

---

## 4. What is the use of a Wait Node?
**Answer:**  
The **Wait Node** holds the process until a condition is met or a specified time has passed.  
It is typically used for:  
- Delays  
- Escalations  
- Waiting for an external update  

---

## 5. If a workflow task is not assigned to anyone due to an incorrect person group or user ID, how can you reassign it manually?
**Answer:**  
We can reassign the task using the **Workflow Administration application**:  
1. Go to **Workflow Administration**.  
2. Search for the workflow instance where it is stuck.  
3. Open the **Assignments** tab.  
4. Select the incorrect task.  
5. From **Select Action → Reassign**.  
6. Choose a new **User, Person Group, or Role**.

---

## 6. What if a user doesn't take action on an Interaction Node?
**Answer:**  
- Use a **Wait Node** after the Interaction Node.  
- Attach an **Escalation** to notify the user or auto-route the workflow to someone else.

---

## 7. Can you make a field mandatory using a Manual Input Node?
**Answer:**  
Yes. In the **Manual Input Node**, you can define fields (e.g., `DESCRIPTION`, `REMARK`) and mark them as **Required**.  
- The workflow will not proceed until the field is filled.  
- Example: Before a PR approval, the requester must provide **justification comments**.

---

## 8. What if a Subprocess Node fails? Does it stop the main workflow?
**Answer:**  
Yes, by default, if a **Subprocess Node fails** (due to error or invalid data), it can stop the **main workflow**.  
To prevent this:  
- Use **Error Handling** within the subprocess.  
- Design the subprocess with its own **Stop Node paths**.

---

## 9. What is Error Handling in Maximo Workflow?
**Answer:**  
**Error Handling** in Maximo Workflow refers to the process of **detecting, managing, and resolving errors** during workflow execution.  
Examples include:  
- Invalid assignments.  
- Missing data.  
- Logic failures.  
- Subprocess errors.  
