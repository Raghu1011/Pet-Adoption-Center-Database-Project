🐾 Pet Adoption Center Database

📘 Project Overview
The **Pet Adoption Center Database** is designed to manage and streamline all operations within an animal adoption center.  
It supports the full workflow — from tracking animals and their medical records to managing adopters, applications, and finalized adoptions.

The system ensures data accuracy, efficient management, and real-time accessibility, improving staff coordination and decision-making.  
It also facilitates better care for animals and smoother adoption experiences for potential pet owners.


🧩 Core Objectives
- Maintain accurate records of **animals, adopters, and staff**.  
- Track **medical history, vaccinations, and adoption applications**.  
- Automate adoption processes through **stored procedures** and **views**.  
- Enforce **data integrity** with constraints, triggers, and auditing.  
- Provide insights through queries and reports for adoption trends.


🗄️ Database Structure

**Main Tables**
1. **Animals** – Details of species, breed, age, gender, and adoption status.  
2. **Medical_Records** – Tracks treatments, examinations, and veterinarians.  
3. **Vaccinations** – Logs vaccines, dates, and administrators.  
4. **Adopters** – Stores adopter contact info, housing, and pet ownership details.  
5. **Adoption_Applications** – Manages application submissions and statuses.  
6. **Adoptions** – Records finalized adoptions (fact table).  
7. **Staff** – Holds staff details, roles, and hire dates.



🧱 SQL Implementation

1. Database Creation
- Creates all tables with appropriate primary and foreign keys, CHECK constraints, and data validation.

2. ERD Diagram
- Shows relationships between all entity tables (Animals, Adopters, Staff, etc.).  
- Fact table: `Adoptions` connects all key relationships.

3. Data Population
- Inserts sample data:
  - 10 rows per dimension table  
  - 20–50 rows for transactional tables (Medical_Records, Vaccinations, etc.)


🧮 Views (Data Insights)

1. Available Animals View
Lists available animals under 5 years old with vaccination data.  
Useful for quickly identifying healthy, adoptable pets.

2. Pending Applications View
Displays pending adoption requests submitted within the last 30 days.  
Helps staff prioritize application reviews.

3. Recent Adoptions by Staff View
Counts adoptions processed by each staff member in the past 3 months.  
Supports performance tracking and efficiency analysis.


🔒 Audit and Triggers
An Animals_Audit table records changes (INSERT, UPDATE, DELETE) to the `Animals` table.  
Each record includes:
- Action type  
- Timestamp (`ChangedOn`)  
- User who performed the action (`ChangedBy`)  

This ensures full traceability and accountability for all modifications.

⚙️Stored Procedure & Function

Stored Procedure: `usp_UpdateAdoptionStatus`
Updates an animal’s adoption status with validation and error handling.

User Defined Function (UDF): `ufn_CalculateAdoptionFee`
Calculates the adoption fee based on species and age, promoting consistency in pricing policies.



🔁 Cursor Example
Procedure `usp_UpdateOldApplications` uses a **cursor** to find pending applications older than 30 days and automatically updates their status to **Expired**.  
This automation supports data maintenance and ensures up-to-date application records.



 📊 Example Queries
- Retrieve all available animals.  
- Join adopter and adoption details for reporting.  
- Analyze staff performance based on processed adoptions.

 📂 Repository Contents
`IFT530_FinalProject.docx` – SQL scripts, triggers, views, procedures, and cursor examples.  
  `IFT530_ProjectSummary.docx` – Overview, table definitions, and database design summary.  
  `README.md` – This documentation file.



Conclusion
The Pet Adoption Center Database enhances operational efficiency through structured data management, integrity enforcement, and automation.  
It serves as a practical model for implementing a **real-world relational database** using SQL Server, emphasizing performance, security, and usability.

**© 2024 | Team 28 | IFT 530 – Advanced Database Management Systems**
