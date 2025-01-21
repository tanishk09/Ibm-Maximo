# Most Frequently Questions Asked in Maximo Interview for Database Configuration.

### 1. What is database configuration in Maximo and what it will do?
Database Configuration (DB Config) in IBM Maximo is a tool used to define and manage the data dictionary of the Maximo application. It allows administrators to modify the database schema without requiring direct interaction with the underlying database.

- **Create, Modify, or Delete Objects (Tables)**: Enables the addition of new objects (database tables) or modification of existing ones, such as adding new attributes (columns) or removing unused ones.
- **Manage Relationships**: Configures relationships between objects to support data association (e.g., defining one-to-many or many-to-many relationships).
- **Index Management**: Allows the creation and management of indexes to improve database query performance.
- **Attribute Configuration**: Enables customization of attributes, such as setting data types, lengths, mandatory fields, and default values.
- **Alias and Domains**: Supports aliasing fields for compatibility and associating domains for attribute value validation.

---

### 2. What are the main object and persistent objects in Maximo?

The **main object** in Maximo is the primary object or table in a module or application that stores core business data. For example:

- **WORKORDER** in the Work Order Tracking application.
- **ASSET** in the Assets application.
- **LOCATIONS** in the Locations application.

The main object is central to the functionality of the application and typically has relationships to other related objects for detailed data storage or transactional records.

### Persistent Object in Maximo

A **persistent object** in Maximo is an object (table) that physically exists in the database. Its data is stored permanently until modified or deleted through the application or database operations.  

Key points about persistent objects:
1. **Physical Representation:** They have a corresponding table in the database.
   - Example: The **WORKORDER** object corresponds to the **WORKORDER** table in the database.
2. **Data Storage:** They store business-critical data, such as work orders, assets, or inventory details.
3. **Customizable:** Attributes (columns) of persistent objects can be added or modified using the Database Configuration tool.
4. **Examples:**
   - **WORKORDER**
   - **ASSET**
   - **INVENTORY**

### Difference Between Main and Persistent Objects
- **Main Object** refers to the primary focus of a module or application.
- **Persistent Object** is a broader term, encompassing all database-backed objects, including main objects, child objects, and other related tables.

---

### 3. How to create a child object in IBM Maximo?
Creating a child object in Maximo involves defining a new object and establishing a relationship with an existing parent object. Here's a step-by-step guide:

### Steps to Create a Child Object in Maximo:

1. **Navigate to the Database Configuration Application:**
   - Log in to Maximo.
   - Go to **System Configuration** > **Platform Configuration** > **Database Configuration**.

2. **Create the New Object:**
   - Click on the **New Row** button to create a new object.
   - Fill in the required details:
     - **Object Name:** Specify the name of the new child object.
     - **Class Name:** Select the appropriate class (e.g., psdi.mbo.custapp.CustomMboSet).
     - **Persistent:** Ensure the checkbox is selected if the object needs to have a corresponding table in the database.
     - **Description:** Provide a brief description of the object.

3. **Define Attributes:**
   - Click on the **Attributes** tab and add the necessary attributes (columns) for the child object:
     - **Attribute Name:** Define the column name.
     - **Data Type:** Select the appropriate data type (e.g., INTEGER, VARCHAR).
     - **Length:** Specify the length (if applicable).
     - **Required:** Check if the field must have a value.
     - **Default Value:** (Optional) Set a default value for the attribute.

4. **Establish a Relationship:**
   - Navigate to the **Relationships** tab of the parent object.
   - Click on **New Row** to define a relationship:
     - **Relationship Name:** Provide a meaningful name for the relationship.
     - **Child Object Name:** Enter the name of the child object.
     - **Where Clause:** Specify the relationship condition, typically linking the parent and child objects via a foreign key.  
       Example: `parentid = :parentid`.

5. **Apply Database Changes:**
   - Save your changes.
   - Navigate to the **Select Action** menu and choose **Apply Configuration Changes** to update the database schema.

6. **Verify and Test:**
   - Confirm the new child object is created successfully in the database.
   - Test the relationship by using tools like the MIF or application records that rely on this relationship.

### Notes:
- **Foreign Key Constraint:** Ensure the child object has a foreign key attribute that links it to the parent object.
- **Access Security:** Update security groups to grant the required access to the new child object if necessary.
- **Application Designer:** Update the relevant application screens to display the child object data.

This process enables extending Maximo's data model to meet specific business needs by organizing and relating data efficiently.

---

### 4. What is the persistent and non-persistent attribute in IBM Maximo

Attributes in IBM Maximo refer to the columns or fields of an object (table). These attributes can be classified as **persistent** or **non-persistent** based on whether they are stored in the database.

### Persistent Attribute

A **persistent attribute** is an attribute whose value is stored in the database. This means it physically exists as a column in a database table.

#### Characteristics:
1. **Stored in the Database:**
   - Values of persistent attributes are saved permanently in the database.
   - They are included in the table schema.

2. **Examples:**
   - **WORKORDER.WONUM** (Work Order Number)
   - **ASSET.ASSETNUM** (Asset Number)
   - **LOCATIONS.SITEID** (Site Identifier)

3. **Use Cases:**
   - Store business-critical data that must be retained and queried.

4. **Modifications:**
   - Can be modified via the Database Configuration application.

### Non-Persistent Attribute

A **non-persistent attribute** is an attribute that does not have a corresponding column in the database. Its value is typically calculated, derived, or used temporarily during runtime.

#### Characteristics:
1. **Not Stored in the Database:**
   - Non-persistent attributes exist only in memory and are not saved in the database.

2. **Purpose:**
   - Used for temporary calculations, display-only fields, or data transformations.

3. **Examples:**
   - A calculated total cost of items in a work order.
   - A field to temporarily store user input before processing.

4. **Defined in the MBO:**
   - Non-persistent attributes are defined in the Maximo Business Object (MBO) class or through automation scripts.

5. **Use Cases:**
   - Temporary display fields in applications.
   - Storing intermediate results in scripts or integrations.
   - Avoiding unnecessary database changes for transient data.

### Key Differences Between Persistent and Non-Persistent Attributes:

| **Aspect**                | **Persistent Attribute**           | **Non-Persistent Attribute**          |
|---------------------------|------------------------------------|---------------------------------------|
| **Storage**               | Stored in the database             | Exists only in memory                  |
| **Database Column**       | Has a corresponding table column   | No corresponding table column          |
| **Usage**                 | Stores permanent data              | Used for temporary or calculated data  |
| **Performance Impact**    | Involves database storage and I/O  | Lightweight, exists during runtime     |
| **Configuration**         | Defined and modified in DB Config  | Defined programmatically or in scripts |

### Interview Answer Example:
"In IBM Maximo, persistent attributes are stored permanently in the database and are part of the object’s table schema, such as `WORKORDER.WONUM`. Non-persistent attributes, on the other hand, are temporary and exist only during runtime for calculations or intermediate data, like a calculated field displayed in the UI. Non-persistent attributes help avoid database overhead for transient data while allowing flexibility in application logic."
