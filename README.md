# 🚀 Azure End-to-End Data Engineering Project

An end-to-end **Azure Data Engineering Pipeline** built using **Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, PySpark, Azure Synapse Serverless SQL, and Power BI** following the **Medallion Architecture (Bronze → Silver → Gold).**

This project demonstrates how raw data is ingested, transformed, stored securely, queried using Serverless SQL, and visualized in Power BI using modern Azure best practices.

---

# 📌 Project Architecture

```
                  AdventureWorks Dataset
                           │
                           ▼
               Azure Data Factory (ADF)
                           │
                           ▼
       Azure Data Lake Storage Gen2 (Bronze)
                           │
                           ▼
        Azure Databricks (PySpark Transformations)
                           │
                           ▼
       Azure Data Lake Storage Gen2 (Silver)
                           │
                           ▼
        Azure Synapse Serverless SQL (Gold Views)
                           │
                           ▼
                     Microsoft Power BI
```

---

# 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| Azure Data Factory | Data Ingestion |
| Azure Data Lake Storage Gen2 | Data Storage |
| Azure Databricks | Data Transformation |
| Apache Spark (PySpark) | ETL Processing |
| Unity Catalog | Data Governance |
| Azure Access Connector | Secure Storage Access |
| Managed Identity | Authentication |
| Azure Synapse Serverless SQL | Data Querying |
| Power BI | Data Visualization |

---

# 📂 Medallion Architecture

## 🥉 Bronze Layer

- Raw AdventureWorks CSV files
- Stored in Azure Data Lake Storage Gen2
- No transformations applied
- Acts as the source of truth

---

## 🥈 Silver Layer

Data transformations were performed using **PySpark** inside Azure Databricks.

### Transformations Performed

- Converted string columns into Date data types
- Created Month and Year columns
- Generated Full Name from customer details
- Split Product SKU and Product Name
- Created calculated columns
- Corrected data types
- Cleaned and standardized datasets

The transformed data was stored in **Parquet** format inside the Silver container.

---

## 🥇 Gold Layer

Business-ready SQL Views were created using **Azure Synapse Serverless SQL**.

Views Created:

- Calendar
- Customers
- Products
- Sales
- Returns
- Territories
- Product Subcategories

These views are consumed directly by Power BI.

---

# 🔐 Security Implementation

Instead of using Storage Account Keys or SAS Tokens, this project implements Azure's modern authentication approach.

Implemented:

- ✅ Managed Identity
- ✅ Azure Access Connector
- ✅ Unity Catalog
- ✅ Storage Credentials
- ✅ External Locations
- ✅ RBAC (Role-Based Access Control)

---

# 🔄 Data Pipeline Workflow

```
AdventureWorks Dataset

        │

        ▼

Azure Data Factory

        │

        ▼

Bronze Layer (CSV)

        │

        ▼

Azure Databricks

        │

        ▼

Silver Layer (Parquet)

        │

        ▼

Azure Synapse Serverless SQL Views

        │

        ▼

Power BI Dashboard
```

---

# 📁 Project Structure

```
Azure-End-to-End-Data-Engineering-Project
│
├── adf/
│   ├── Pipeline JSON
│   └── Screenshots
│
├── databricks/
│   ├── Bronze_to_Silver.ipynb
│   ├── Transformations.ipynb
│   └── Screenshots
│
├── synapse/
│   ├── Create_Schema.sql
│   ├── Create_Gold_Views.sql
│   ├── Test_Gold_Views.sql
│   └── Legacy_External_Tables.sql
│
├── powerbi/
│   ├── AdventureWorks.pbix
│   └── Dashboard Screenshot
│
├── architecture/
│   ├── Architecture Diagram
│   └── Medallion Architecture
│
├── screenshots/
│
└── README.md
```

---

# 📊 PySpark Transformations

Examples of transformations performed:

- Date Formatting
- Full Name Creation
- Product SKU Extraction
- Product Name Extraction
- Month & Year Generation
- Data Type Conversion
- Calculated Columns
- Null Handling

---

# 💡 Challenges Faced

### Challenge 1

Connecting Azure Databricks to Azure Data Lake Storage Gen2.

### Solution

Implemented:

- Azure Access Connector
- Managed Identity
- Unity Catalog
- Storage Credentials
- External Locations

---

### Challenge 2

Reading Silver Layer inside Azure Synapse Serverless SQL.

### Solution

Created:

- Database Scoped Credential
- External Data Source
- External File Format
- SQL Views using OPENROWSET

---

### Challenge 3

Power BI Authentication Error

```
Cannot find the CREDENTIAL...
```

### Solution

Recreated SQL Views using the configured External Data Source and Managed Identity.

---

# ⭐ Key Features

- End-to-End Azure Data Engineering Pipeline
- Medallion Architecture
- Serverless SQL Analytics
- Secure Authentication using Managed Identity
- Unity Catalog Integration
- PySpark Data Transformation
- Power BI Reporting
- Modern Azure Best Practices

---

# 🚀 Project Enhancements

Compared to the original implementation, this project was modernized using current Azure best practices.

| Original Tutorial | This Project |
|-------------------|--------------|
| Service Principal | Managed Identity |
| Legacy Databricks Access | Unity Catalog |
| Direct Storage Access | Access Connector |
| Storage Keys | RBAC + Managed Identity |
| Hardcoded Storage URLs | External Data Sources |
| Tutorial Implementation | Modern Azure Implementation |

---

# 📈 Future Enhancements

- Delta Live Tables
- Incremental Data Loading
- Azure Key Vault Integration
- CI/CD using Azure DevOps
- Data Quality Validation
- Automated Monitoring

---

# 📸 Project Screenshots

## Azure Data Factory

(Add Screenshot)

---

## Azure Databricks

(Add Screenshot)

---

## Unity Catalog

(Add Screenshot)

---

## Azure Synapse Serverless SQL

(Add Screenshot)

---

## Power BI Dashboard

(Add Screenshot)

---

# 🎯 Learning Outcomes

Through this project I gained hands-on experience with:

- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks
- Apache Spark (PySpark)
- Azure Synapse Serverless SQL
- Unity Catalog
- Managed Identity
- Azure RBAC
- Power BI
- Medallion Architecture
- Cloud Data Engineering Best Practices

---

# 👨‍💻 Author

**Gauri Bhonsle**

Azure Data Engineering | Data Engineering | Cloud Analytics
