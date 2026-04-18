## 12. Monitoring & Alerting Standards
[[_TOC_]]

Monitoring and alerting ensure that the Data Platform operates reliably and that issues are detected and resolved quickly. Monitoring must cover infrastructure, applications, and data pipelines, in compliance with the **NZISM**, Stats NZ ICT monitoring policies, and the platform’s **observability standards (Section 4)**.  

**Key expectations:**  

### 12.1 Monitoring Scope
- Monitoring must include infrastructure (compute, storage, networking), platform services (Databricks, Unity Catalog, ADLS, Power BI), and data pipelines.  
- Coverage must extend across environments (Dev, Test, UAT, Production) with higher rigor in UAT and Production.  
- All monitoring must be centralised in approved observability platforms to ensure consistent coverage and governance oversight.  

### 12.2 Metrics & Telemetry
- Monitoring must capture the **three pillars of observability**: metrics, logs, and traces.  
- Standard metrics must include system utilisation, job success/failure, error rates, latency, throughput, and queue sizes.  
- Data freshness and completeness metrics must be collected to validate timeliness of ingestion and processing.  
- Telemetry data must be retained for at least 180 days (see Section 4) for audit and forensic analysis.  

### 12.3 Alerting & Escalation
- Alerts must be configured for critical system failures, SLA/SLO breaches, and data quality incidents.  
- Alert severity levels must be defined (critical, high, medium, low) with corresponding response time targets.  
- Alerts must integrate with **IvantiCloud ITSM** for incident management and escalation.  
- Runbooks must exist for all critical alerts, defining investigation and remediation steps.  
- Alert noise must be minimised by tuning thresholds and using correlation to avoid alert fatigue.  

### 12.4 Data Pipeline Health
- Pipelines must be monitored for **latency, throughput, error rates, and freshness** to ensure reliable operation.  
- Automated alerts must trigger on unexpected delays, backlogs, or failure patterns.  
- Observability dashboards must visualise pipeline health in real time for both platform and product teams.  
- Quality validation results (see Section 8) must be integrated into pipeline health monitoring.  

### 12.5 Governance & Continuous Improvement
- Monitoring and alerting standards must be reviewed annually to align with evolving NZISM and ICT policies.  
- Incident post-mortems must include assessment of monitoring and alerting coverage, with lessons integrated into improvements.  
- Product teams must review alert dashboards regularly to ensure pipeline-specific monitoring remains relevant.  
- Platform-level monitoring metrics and compliance must be reported to Stats NZ governance forums.  
****