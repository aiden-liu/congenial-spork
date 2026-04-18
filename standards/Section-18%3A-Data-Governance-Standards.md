## 18. Data Governance Standards
[[_TOC_]]

Data governance ensures that all datasets and platform services are **trusted, well-documented, and responsibly managed**. Governance provides clarity of ownership, compliance with policy and legislation, and alignment with the **[5 Safes model](https://www.stats.govt.nz/integrated-data/how-we-keep-integrated-data-safe/)**. Governance on the Data Platform must comply with the **[Data and Statistics Act 2022](https://www.legislation.govt.nz/act/public/2022/0039/latest/LMS418574.html)**, **[Privacy Act 2020](https://www.legislation.govt.nz/act/public/2020/0031/latest/LMS23223.html)**, **[NZISM](https://nzism.gcsb.govt.nz/)**, Stats NZ’s internal policies, and obligations under **[Te Tiriti o Waitangi](https://www.waitangitribunal.govt.nz/en/about/the-treaty/about-the-treaty)**.  

**Key expectations:**  

### 18.1 Framework & Compliance
- The platform must operate under Stats NZ’s **[Data Governance Framework](https://statsnewzealand.sharepoint.com/:w:/r/sites/KOHINGA-TROFFICE/Shared%20Documents/Strategy%20System%20Map/05_Design%20Meta%20Model/Operational_Data_Governance_Framework_DraftV0.2.docx?d=wc7716538d4be46c892f606335d25dbf2&csf=1&web=1&e=wgUvY5)**, ensuring consistency with enterprise policy.  
- All governance practices must comply with **[New Zealand Information Security Manual - NZISM](https://nzism.gcsb.govt.nz/)**, **[Stats NZ confidentiality rules](https://statsnewzealand.sharepoint.com/sites/KOHINGA-MADHUB/SitePages/ConfidentialityNetwork.aspx)**, and relevant international standards for statistical data.  
- Governance reviews must be aligned with enterprise-wide risk and assurance processes.  

### 18.2 Roles & Responsibilities
- **Product teams** are responsible for governance of their datasets, including metadata, classifications, and access controls.  
- The **Platform team** is responsible for governance of shared services, Unity Catalog, and enforcement of baseline standards.  
- **Governance boards** (e.g., Data Governance Board, Security and Privacy forums) oversee compliance, approve exceptions, and resolve disputes.  
- Each dataset must have a **designated steward/owner**, recorded in Unity Catalog metadata.  

### 18.3 Metadata & Unity Catalog
- **Unity Catalog** must be the **system of record** for all metadata, including ownership, classifications, retention, quality rules, and access policies.  
- Metadata must be complete and kept up to date, with quality checks to ensure accuracy.  
- All datasets must include governance metadata fields: steward, purpose, sensitivity, retention, PII classification, access rules.  
- Lineage metadata must be captured for all transformations and accessible for audit.  

### 18.4 Māori Data Governance & Te Tiriti
- Governance must respect **[Māori Data Sovereignty](https://statsnewzealand.sharepoint.com/:b:/r/sites/KOHINGA-MAORIPART/CoreDocuments/WAI2570_Fact%20Sheet%20-%20Maori%20Data%20Sovereignty.pdf?csf=1&web=1&e=iILXNf)**  and reflect Stats NZ’s obligations under **[Te Tiriti o Waitangi](https://www.waitangitribunal.govt.nz/en/about/the-treaty/about-the-treaty)**.  
- Māori data, or data with relevance to Māori communities, must undergo review for cultural sensitivity and governance alignment.  
- Māori Strategy & Partnerships must be consulted on governance decisions involving Māori data.  
- Governance metadata must include indicators for Māori data classifications and stewardship.  

### 18.5 Governance Processes & Reporting
- Governance compliance must be reported quarterly to Stats NZ governance forums.  
- Policies, standards, and governance processes must be documented in SharePoint for accessibility.  
- All standards updates must follow a formal governance approval workflow and include version control and changelogs.  
- Data governance must integrate with **[IvantiCloud ITSM](https://statisticsnz-ism.ivanticloud.com/Default.aspx?NoDefaultProvider=True)** for policy exceptions, approvals, and tracking.  
**Example:**  
If a dataset contains fields that cannot be fully masked without breaking statistical utility, the product team must raise a “Data Policy Exception” in IvantiCloud ITSM. The exception request must document the risk, justify why the field cannot be masked, outline compensating controls, and identify approved users. Data governance reviews and approves the exception, and IvantiCloud tracks the approval record, expiry date, and required follow-up reviews.

- Governance maturity must be reviewed biennially against Stats NZ’s Data Governance Framework and Enterprise Steady States.  
