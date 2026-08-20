# Apache Kafka Supplier Alert Streaming Platform
## The Problem
Supplier alerts fail operationally when events are duplicated, unacknowledged, or escalated without accountable consumer evidence.
## The Solution
This platform models supplier alert streaming with controlled topic publication, consumer acknowledgement, manager escalation, and a complete audit trail.
## Live Demo & Tech Stack
The service binds to `0.0.0.0:19300`. The stack uses Node.js, event-streaming patterns, Express, Vitest, and GitHub Actions.
## Local Setup & Run Instructions
```bash
npm install
npm test
npm start
```
## System Documentation (Mermaid.js)
### System Architecture Diagram
```mermaid
flowchart LR
  Producer-->Topic[Supplier alert topic]
  Topic-->Consumer
  Consumer-->Manager
  Manager-->Audit[Audit events]
```
### Entity-Relationship Diagram
```mermaid
erDiagram
  ALERT_EVENT ||--o{ AUDIT_EVENT : records
  ALERT_EVENT { string id string supplier string topic string state }
  AUDIT_EVENT { string id string action string actor string role }
```
### Data Flow Diagram
```mermaid
flowchart TD
  Publish-->Acknowledge-->Escalate-->Audit
```
### Use Case Diagram
```mermaid
flowchart LR
  Producer-->PublishAlert
  Consumer-->AcknowledgeAlert
  Manager-->EscalateAlert
```
### Sequence Diagram
```mermaid
sequenceDiagram
  participant P as Producer
  participant T as Topic
  participant C as Consumer
  P->>T: Publish supplier alert
  C->>T: Acknowledge event
  T-->>P: Escalated audit state
```
## Owner
Created and maintained by Kholipha Ahmmad Al-Amin.
Software Engineer and AI Specialist
Founder and CEO of EquiSaaS BD
Principal Consultant at AR IT Consultancy
Full Stack Developer and SaaS Product Builder
### Official links
Portfolio: https://kholipha-ahmmad-al-amin.equisaas-bd.com/
GitHub: https://github.com/kholipha-ahmmad-al-amin
LinkedIn: https://www.linkedin.com/in/kholipha-ahmmad-al-amin
X: https://x.com/al_amin5519
Facebook: https://www.facebook.com/kholipha.ahmmad.al.amin
Instagram: https://www.instagram.com/kholipha.ahmmad.al.amin
## Ownership
This project was created and is maintained by Kholipha Ahmmad Al-Amin.

