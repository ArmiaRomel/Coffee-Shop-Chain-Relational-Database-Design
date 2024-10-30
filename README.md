# Coffee Shop Chain Relational Database Design

## Project Overview
This project involves designing and creating a relational database system for a coffee shop chain, aimed at improving operational efficiencies and supporting data-driven decisions by its executives. Using PostgreSQL, I developed an Entity-Relationship Diagram (ERD) and a fully normalized database schema. To enhance data accessibility and allow for further use by other systems, I uploaded key data views to MySQL via phpMyAdmin. This schema encompasses essential tables, including `staff`, `sales_outlet`, `sales_transaction`, `sales_detail`, `customer`, `product` and `product_type`, managing aspects such as tracking sales transactions, customer information, product details, and staff assignments across multiple systems.

## Project Features
- **Database Design and Normalization**: Developed a fully normalized database schema to ensure data integrity and reduce redundancy.
- **Cross-Platform Data Integration**: Integrated data views and materialized views across PostgreSQL, MySQL, and IBM DB2 on Cloud for enhanced accessibility and analysis.
- **Comprehensive Data Views**: Created specialized views to streamline data reporting and optimize query performance.

## Technologies Used
- **Databases**: PostgreSQL (pgAdmin), MySQL (phpMyAdmin), IBM DB2 on Cloud
- **Languages**: SQL
- **Tools**: pgAdmin, phpMyAdmin, ERD modeling tool

## Database Design Process

1. **Data Source**: 
   - Used a sample data subset [Coffee shop sample data](https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/12/beanie-coffee-1113?utm_source=Exinfluencer&utm_content=000026UJ&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDB0110ENSkillsNetwork24601058-2021-01-01&utm_medium=Exinfluencer&utm_term=10006555) as the foundation for initial tables and attributes.
     ![existing_data](https://github.com/user-attachments/assets/a09cda30-e06a-4f91-aba3-14f1f22c3c0a)

2. **Creating the Database**: 
   - Created a PostgreSQL database named `COFFEE` and populated it with tables using SQL scripts:
      - [SQL file for Database Creation and Normalization](https://github.com/user-attachments/files/17575208/GeneratedScript.zip): This SQL file includes the normalized ERD structure, extracted from PostgreSQL after defining relationships and applying normalization.
      - [SQL file for Initial Data Insertion](https://github.com/user-attachments/files/17575241/CoffeeData.zip): This file is used to populate the database tables with initial data.

3. **Normalization and Schema Refinement**:
   - Conducted normalization on tables to meet the Second Normal Form (2NF):
     - **`sales_transaction` Table**: Created a new `sales_detail` table to eliminate repeating rows where multiple products were tied to a single transaction, thus achieving 2NF.
     - **`product` Table**: Created a `product_type` table to remove redundancy in the `product_category` and `product_type` columns.
   - **Keys and Relationships**: Defined primary and foreign keys and established relationships across tables to ensure referential integrity within the database.
   - ERD screenshot: ![ERD](https://github.com/user-attachments/assets/ae908188-4e8d-4c63-8e5a-36df067c2edc)

4. **Data Views and Query Optimization**:
   - Created the following views to enhance data accessibility and optimize reporting:
     - **`staff_locations_view`**: This view provides insights into the distribution of staff across locations, streamlining workforce management.
     - **`product_info_mview`**: This materialized view provides a stored snapshot of product data, optimizing reporting on product categories and types.
       View query result screenshot: ![View Query Result](https://github.com/user-attachments/assets/b2d7cd6d-fc5e-416b-ba8d-8995a10695d9)
       Materialized view query result screenshot: ![Materialized View Query Result](https://github.com/user-attachments/assets/92802093-0a1d-4023-b481-b8efe0683782)

5. **Cross-Platform Data Export**:
   - Exported `staff_locations_view` and `product_info_mview` to CSV format:
      - [CSV file of staff locations view](https://github.com/user-attachments/files/17575398/staff_locations_view.csv)
      - [CSV file of product info materialized view](https://github.com/user-attachments/files/17575400/product_info_m-view.csv)
   - Imported these CSVs into MySQL via phpMyAdmin for accessibility:
      - Uploaded view screenshot: ![View Uploaded to MySQL](https://github.com/user-attachments/assets/1c87a1ed-6d49-46e1-9239-d28ff02b4365).
      - Uploaded materialized view screenshot: ![Materialized View Uploaded to MySQL](https://github.com/user-attachments/assets/833ca26d-c837-476f-87e1-c1bed2fbbcb9).
   - Additionally, uploaded `staff_locations_view` to IBM DB2 on Cloud to make the data accessible for cloud-based applications ![IBM DB2 Query Result](https://github.com/user-attachments/assets/d522b0ef-a650-4228-8d40-8c5a8f87602a)
