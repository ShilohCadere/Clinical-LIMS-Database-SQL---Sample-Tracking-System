# Clinical LIMS Database

Relational database system for structured sample tracking, metadata management, and laboratory workflow organization within a clinical NGS data pipeline.

## System Context

This LIMS represents the data infrastructure layer of a clinical NGS system, enabling traceability of samples, instruments, and project-based workflows.

It integrates with:

- NGS QC Pipeline → sequencing quality validation
- Genomic Toolkit → sequence processing utilities
- LIMS Database (this system) → structured sample and workflow tracking

Together, these components support end-to-end NGS data lifecycle management.

## Data Model Overview

Core entities in the system:

- Projects → client-driven sequencing requests
- Samples → biological materials linked to projects
- Instruments → sequencing and processing hardware
- Employees → operational and processing roles
- Supplies → laboratory inventory tracking

## Entity Relationships
- A Project contains multiple Samples
- A Sample belongs to one Project
- An Instrument may be associated with Samples and/or Employees
- Employees manage and execute laboratory operations

## Core System Features
**Relational Schema Design**

Normalized database structure with enforced primary and foreign key constraints to maintain data integrity across laboratory entities.

**Automated Key Management**

Sequence-based surrogate key generation for consistent entity identification across all core tables.

**Audit Tracking**

Automatic recording of:

- record creation timestamps
- modification timestamps
- user attribution

## Data Abstraction Layer (Views)

Simplified query interfaces for:

- Employees
- Projects
- Samples
- Instruments
- Supplies

## Performance Optimization

Indexing strategy implemented for:

- batch-level sample tracking
- foreign key joins
- high-frequency query paths

## Workflow Example

Typical system usage flow:

1. A Project is created for a sequencing request
2. One or more Samples are registered under the project
3. Samples are associated with Instruments for processing
4. Employees manage and execute laboratory operations
5. Data is queried through structured views for downstream QC and reporting

## Technology Stack
- SQL (Oracle dialect)
- Sequences for key generation
- Triggers for automation (audit + IDs)
- Views for query abstraction
- Indexing for relational performance

## System Role

This database functions as the structural layer of a clinical NGS pipeline ecosystem:

- LIMS Database → sample and workflow tracking
- NGS QC Pipeline → quality evaluation and decisioning
- Genomic Toolkit → sequence processing utilities

This architecture models a simplified clinical bioinformatics data system from sample intake to sequencing validation.

## Design Focus
- Traceable sample and workflow state management
- Structured relational data modeling
- Auditability for operational tracking
- Compatibility with downstream bioinformatics pipelines

## Future Enhancements
- REST API layer for programmatic access
- Integration with Python-based QC pipeline tools
- Schema normalization review (3NF refinement)
- Role-based access control (RBAC) implementation

## Author

### Shiloh Cadere
### Bioinformatics Analyst | Clinical NGS Pipelines | Python • SQL • R
