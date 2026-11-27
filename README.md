# NGABO_20251SEN097_EduCore

A centralized Oracle Database schema and modular PL/SQL engine designed to enforce e-learning business rules—including prerequisite validation, seat limits, automated grading, and certificate issuance—directly inside atomic database transactions.

## Overview
E-learning platforms often scatter critical academic rules across fragmented application queries, risking race conditions, partial updates, and inconsistent records. **EduCore** solves this by placing core academic logic inside Oracle PL/SQL packages, triggers, and custom exceptions so every enrollment, grade calculation, and certificate record remains accurate and auditable.

## Key Features
- **Enrollment & Prerequisite Validation:** Verifies course seat capacity, active enrollment status, and completed prerequisite courses before committing signups.
- **Automated Weighted Grading:** Calculates assessment scores, applies late-submission rules, and updates overall course completion status.
- **Batch Cohort Processing:** Uses `BULK COLLECT` and `FORALL` to process cohort progress and overdue alerts efficiently.
- **Tamper-Resistant Certification:** Validates completion thresholds and issues unique, auditable certificate records.
- **Immutable Audit Trail:** Logs enrollment and grade changes via database triggers for academic accountability.

## Project Structure
```text
NGABO_20251SEN097_EduCore/
├── schema/       # DDL scripts for tables, constraints, indexes, and sequences
├── packages/     # PL/SQL package specifications (.pks) and bodies (.pkb)
├── triggers/     # Audit and data-integrity triggers
├── data/         # Seed scripts and sample dataset loaders (e.g., OULAD)
├── tests/        # PL/SQL test blocks and exception verification scripts
└── README.md
