# 4. Observability Standards  

Observability ensures that all Data Platform components are **measurable, diagnosable, and accountable**. Pipelines, services, and infrastructure must emit consistent logs, metrics, and events to support reliability, cost control, compliance, and statistical assurance.  
[[_TOC_]]

**Key expectations:**  

### 4.1 Structured Logging  
- All jobs, pipelines, and services must emit **structured logs** in JSON or key–value format.  
- Logs must include standard fields:  
  - `pipeline_id`, `run_id`, `ess_stage`, `dataset_id`  
  - `user_id` (or service principal), `cluster_id`  
  - `dq_pass_rate`, `record_count`, `cost_estimate_nzd`  
  - `start_time`, `end_time`, `duration`  
- Sensitive information (PII, security tokens, credentials) must **never be logged**.  
- Logs must be streamed to centralised observability systems (e.g., Azure Monitor, Log Analytics, Databricks Monitoring).  
- Logs must support correlation across environments and ESS boundaries.  

### 4.2 Metrics  
- Pipelines must emit **operational metrics** including throughput, latency, error counts, and cost/DBU usage.  
- Data Quality metrics (validation pass rate, failed constraints, schema drift counts) must be included in standard telemetry.  
- Security metrics (access denials, privilege escalations, failed authentications) must be monitored.  
- Metrics must be published to Stats NZ’s observability platform and integrated with alerting rules.  

### 4.3 Dashboards and Monitoring  
- Each **product team** must maintain at least one **product-level observability dashboard** covering their pipelines, datasets, and costs.  
- Each Enterprise Steady State (ESS) must have its own operational dashboard that reports run status, pass/fail rates, cost profiles, data availability, and SLIs/SLOs. A single workspace may host multiple ESSs, and therefore may have multiple ESS dashboards. These dashboards are product-level, not workspace-level.
- Dashboards must be accessible to both engineers and managers, with views tailored for operational detail and governance oversight.  
- Standard dashboards must be provided at the platform level (data quality, cost, reliability, utilisation).  

### 4.4 Retention and Auditability  
- Logs and metrics must be retained centrally for a minimum of **180 days** to support audits, reproducibility, and governance reviews.  
- Retention rules must comply with Stats NZ security, privacy, and Māori data sovereignty obligations.  
- Aggregated historical observability data must be available for FinOps reporting and statistical assurance.  

### 4.5 Integration with DevSecOps and CI/CD  
- CI/CD pipelines (see Section 3.3) must validate that observability hooks are present before deployments.  
- Structured logging must replace print/debug statements (see Section 3.4 Code Quality).  
- Test failures, data quality exceptions, and security violations must automatically emit events to monitoring systems.  
- Pipelines must fail deployment if observability integration is missing or disabled.  

### 4.6 Governance and Continuous Improvement  
- Observability patterns must be reviewed and standardised across teams.  
- Dashboards and metrics must be part of governance reporting and reviewed in Data Platform forums.  
- Post-incident reviews must capture lessons into new metrics or logging patterns.  
- Observability standards will evolve with platform maturity; minimum baselines from v1.7.2 remain mandatory.  
