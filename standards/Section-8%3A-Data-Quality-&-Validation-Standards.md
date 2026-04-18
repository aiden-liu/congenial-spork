## 8. Data Quality & Validation Standards
[[_TOC_]]
Data quality underpins the **trustworthiness, reliability, and usability** of all outputs from the Data Platform. All datasets and pipelines must meet Stats NZ’s internal governance requirements, the **NZISM**, and international statistical best practices. Data validation must be embedded in pipelines, monitored through observability, and owned by product teams.  

**Key expectations:**  

### 8.1 Schema & Structure Validation
- Pipelines must validate schema **consistency, accuracy, validity, completeness, timeliness, and uniqueness**.  
- Schema enforcement and constraints (e.g., NOT NULL, type checks) must reject invalid records promptly.  
- Missing mandatory columns, unexpected columns, or type mismatches must fail the pipeline.  
- Schema drift must be logged and reported, with automated alerts to product teams.  
- **Delta Live Tables (DLT)** must be leveraged where possible to define expectations and automatically drop or quarantine non-conforming records.  
- Schema validation outcomes must be recorded in observability dashboards (see Section 4).  

### 8.2 Data Profiling & Anomaly Detection
- Datasets must be **profiled regularly** to detect anomalies in record counts, distributions, and data types.  
- Significant deviations from historical patterns (e.g., 30% drop in counts, unexpected null spikes) must trigger alerts.  
- Product teams must configure anomaly thresholds appropriate to their data product.  
- **Lakehouse Monitoring** must be used to track freshness and completeness automatically, with drift detection and alerts configured for missing data, duplicates, or distribution changes.  
- Profiling metrics and monitoring insights must be published to observability dashboards and surfaced via **Unity Catalog lineage** for governance oversight.  

### 8.3 Statistical Validation
- For statistical datasets, validation must include **coherence, consistency, and accuracy checks** aligned to Stats NZ methodology.  
- Validation rules must be documented in the pipeline design and linked to metadata in Unity Catalog.  
- Derived indicators must be tested for plausibility against expected ranges and trends.  
- Validation of statistical outputs must be peer-reviewed within product teams.  
- Validation logic and quality metrics must be captured in Unity Catalog for end-to-end lineage and audit.  

### 8.4 Error Handling & Remediation
- Data quality failures must cause pipelines to **fail fast** and prevent invalid data from propagating downstream.  
- All validation failures must be logged with structured details (dataset, column, rule, timestamp, failure type).  
- Automated remediation (e.g., retries, quarantine zones) may be used but must not overwrite or discard data silently.  
- Product teams must implement documented playbooks for responding to data quality incidents.  

### 8.5 Automation & CI/CD Integration
- Data quality tests must be part of **CI/CD pipelines** and executed automatically on code changes.  
- Test definitions (see Section 3.2) must cover schema, content, and statistical rules.  
- Pipelines must fail deployment if mandatory data quality tests are missing or disabled.  
- Results of CI/CD validation runs must be attached to change records in IvantiCloud ITSM (see Section 7).  

### 8.6 Governance & Continuous Improvement
- Product teams own data quality monitoring within their pipelines.  
- The Platform team provides **reusable frameworks, libraries, and observability integration** for consistency.  
- Data quality results must be visible in governance dashboards and reviewed in platform forums.  
- **Lakehouse Monitoring indicators** must be included as part of governance dashboards for platform-level visibility.  
- **Unity Catalog** must capture metadata about validation rules and quality checks for management and audit.  
- Thresholds, rules, and validation coverage must evolve with dataset maturity and user feedback.  
- Lessons learned from incidents must be incorporated into updated validation standards.  
