# Laboratory Information Management System (LIMS)

Relational database system designed to model laboratory sample tracking, instrument usage, and project-based workflow management in a structured research environment.

---

## Overview

This project implements a simplified Laboratory Information Management System (LIMS) using a relational database design. It models how biological or chemical samples move through a lab workflow—from project assignment to sample processing and instrument usage.

The system emphasizes:
- structured sample tracking
- instrument assignment and status management
- project-based workflow organization
- data integrity through relational constraints

---
## System Context

This LIMS models a laboratory workflow where biological or environmental samples are tracked through experimental processing, instrument usage, and project-based analysis requests.

The system prioritizes traceability of samples, operational tracking of instruments, and structured association between laboratory work and client-driven projects.

---
## System Design

The database is structured around core laboratory entities:

- **Employees** manage and process laboratory work
- **Projects** define analytical requests from clients
- **Samples** represent physical lab materials linked to projects
- **Instruments** are used to process samples
- **Supplies** track lab inventory usage

---

## Entity Relationships

- A **Project** can have multiple **Samples**
- A **Sample** belongs to one **Project**
- An **Instrument** may be assigned to an **Employee** and/or **Sample**
- **Employees** support instrument operation and sample processing

---

## Key Features

### Relational Schema Design
- Normalized table structure for core lab entities
- Primary and foreign key constraints for data integrity

### Automated Key Management
- Sequence-generated surrogate keys for all major entities

### Audit Trail Support
- Automatic tracking of:
  - record creation
  - modification timestamps
  - user attribution

### Views for Data Abstraction
- Simplified access layers for:
  - Employees
  - Projects
  - Samples
  - Instruments
  - Supplies

### Indexing Strategy
- Optimized lookup performance for:
  - batch tracking
  - foreign key relationships

---

## Example Use Case

This system could support workflows such as:

1. A client submits a **Project**
2. The lab creates one or more **Samples**
3. Samples are assigned to **Instruments**
4. Employees process and track sample status
5. Results and workflow state are queryable via views

---

## Technologies Used

- SQL (Oracle dialect)
- Sequences for surrogate keys
- Triggers for automation
- Views for abstraction
- Indexing for query performance

---

## Design Intent

This system was designed to simulate a real-world laboratory environment where:
- samples must be traceable
- instruments require assignment tracking
- workflows depend on structured data relationships
- auditability is required for operational integrity

---

## Portfolio Role

This project represents the **data infrastructure layer** of my bioinformatics portfolio:

- Genomic Toolkit → sequence analysis tooling
- NGS QC Pipeline → workflow processing logic
- LIMS Database → structured biological data management system

Together, these demonstrate end-to-end understanding of biological data systems.

---

## Future Improvements

- REST API layer for database access
- Integration with Python-based pipeline tools
- Enhanced normalization (3NF validation pass)
- Role-based access control (RBAC)
