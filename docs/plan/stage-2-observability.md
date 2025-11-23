# Stage 2 – Observability & Monitoring (Days 13–22)

**Goal:**  
Build an observability stack that includes metrics, logs, alerting and at least one full incident + RCA + postmortem.

By the end of this stage you will have:

- Prometheus + Grafana running.
- Logs stack (Loki or ELK).
- At least one realistic incident scenario with RCA and postmortem.
- Dashboards and alerts configured.

---

## Outcomes / Deliverables

By the end of Stage 2 you should have in GitHub:

- Folder (example): `projects/observability-stack/`
- Docker compose files or Kubernetes manifests for:
  - Prometheus
  - Grafana
  - Loki / ELK (at least one logs solution)
- Sample app or test targets that expose metrics and logs.
- Dashboards exported / documented (JSON or screenshots).
- A postmortem document:
  - File: `docs/incident-01-postmortem.md`

---

## Day-by-Day Plan

### Day 13 – Install Prometheus & Grafana

- Choose deployment method:
  - Docker Compose
  - Kubernetes (kind / minikube / existing cluster)
  - Single VM with containers
- Install:
  - Prometheus
  - Grafana
- Confirm:
  - Prometheus UI is accessible.
  - Grafana UI is accessible.

**Definition of Done:**

- Basic observability stack up and running.
- `docker-compose.yml` or K8s manifests stored in repo.

---

### Day 14 – Metrics Collection & First Dashboard

- Configure Prometheus to scrape:
  - A sample app (e.g., simple HTTP service) **or**
  - Node exporter / system metrics
- In Grafana:
  - Create a new dashboard.
  - Add basic panels (CPU, memory, requests, error rate if available).

**Definition of Done:**

- At least one working dashboard in Grafana.
- Screenshot saved in `docs/screenshots/`.

---

### Day 15 – Alerts & Notifications

- Define alerting rules in Prometheus:
  - Example thresholds (CPU > X%, high error rate, etc.).
- Set up Alertmanager (if not already).
- Configure notifications:
  - Email or Slack (test channel is enough).
- Trigger a test alert (by simulation or configuration).

**Definition of Done:**

- At least one alert rule configured and triggered.
- Notes on how notifications are wired.

---

### Day 16 – Logs Stack (Loki or ELK)

- Choose logs solution:
  - Loki (with Promtail) **or**
  - ELK (Elasticsearch, Logstash, Kibana)
- Deploy the chosen stack:
  - Using Docker or Kubernetes.
- Ingest logs from:
  - Application logs **or**
  - System logs.

**Definition of Done:**

- Logs are visible in Loki/ELK UI.
- Document how logs flow from source to storage.

---

### Day 17 – Connect Logs to an Application

- Pick one test service or app:
  - Simple web app, API or system service.
- Ensure:
  - Logs from that service are shipped to the logs stack.
- Think about:
  - Log structure (JSON vs plain text).
  - Useful fields (request id, correlation id, user id).

**Definition of Done:**

- You can filter logs for the specific app/service.
- At least one example log query documented in notes.

---

### Day 18 – Design an Incident Scenario

- Define a realistic failure scenario, for example:
  - High error rate (HTTP 500).
  - Increased latency.
  - CPU/memory saturation.
  - Service unavailable.
- Decide:
  - What symptoms will appear in metrics.
  - What you expect to see in logs.

**Definition of Done:**

- Incident scenario written in `docs/incident-01-scenario.md`
  - Context
  - Symptoms
  - Expected monitoring and logs signals.

---

### Day 19 – Simulate Incident & Do RCA

- Trigger the incident (in a safe test environment), for example:
  - Stop a service.
  - Introduce a bug in a test branch.
  - Overload the service artificially.
- Use:
  - Grafana dashboards.
  - Logs stack.
- Perform RCA:
  - Identify root cause.
  - Explain the chain of events.

**Definition of Done:**

- Notes for RCA written down.
- Main metrics and log queries used for the investigation are documented.

---

### Day 20 – Write Postmortem

- Create `docs/incident-01-postmortem.md` with sections:

  - Summary
  - Impact
  - Timeline
  - Root Cause
  - Detection
  - Resolution
  - Corrective Actions / Next Steps

- Add specific:
  - Screenshots of dashboards (if possible).
  - Links to log queries (if possible).

**Definition of Done:**

- Postmortem is clear and readable.
- Someone else could understand what happened just from this document.

---

### Day 21 – SLO / SLI Dashboard

- Define simple SLIs:
  - Availability (% of successful requests)
  - Error rate
  - Latency (p95, p99 if applicable)
- Build a Grafana dashboard:
  - Panels showing these SLIs over time.
- Optionally define SLOs:
  - For example: 99% availability over 30 days.

**Definition of Done:**

- SLO/SLI dashboard is created.
- SLIs are clearly documented in notes or the postmortem.

---

### Day 22 – Cleanup & Publish

- Review:
  - Prometheus, Grafana, logs stack configuration.
  - Dashboards and alert rules.
- Clean up:
  - Remove unused files or test configs.
  - Make sure no secrets are stored in Git.
- Push to GitHub:
  - Code (compose/manifests).
  - docs (incident scenario, RCA, postmortem, screenshots).

**Definition of Done:**

- Stage 2 is fully visible in the repo.
- You can show this as an “Observability & Incident Response” demo project.

