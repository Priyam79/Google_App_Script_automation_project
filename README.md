# Railway BOQ & Material Requisition Automation System
Overview
An event-driven, end-to-end workflow automation engine designed to digitize field material requests, validate real-time budget constraints, and deliver live operational analytics. This project addresses the operational delays and human errors typical of manual data entry in site management.

## Problem Statement
In field engineering operations, site supervisors frequently submit material requisitions manually. Back-office teams must then transcribe these requests, look up item costs, calculate project budget impacts, and approve or flag orders. This manual processing creates data entry bottlenecks, delays field approvals, and increases the risk of budget overruns.

## Solution Architecture
### This system automates the entire ingestion-to-reporting lifecycle using Google Workspace tools and custom Apps Script logic:

1. Field Ingestion (Google Forms): Capture structured requisition data (Site Location, Engineer Name, BOQ Code, Quantity) directly from field supervisors.

2. Automated Processing Backend (Google Apps Script):

Trigger Execution: Listens for On Form Submit events to process new entries instantly without manual intervention.

Dynamic Lookup & Validation: Cross-references submitted BOQ Codes against master allocation tables (BOQ_Master) to pull unit costs and historical expenditure.

Real-time Cost Calculations: Calculates total request value and evaluates cumulative spending against total budget allowances.

Automated Status Flagging: Dynamically writes calculated values (Unit Cost, Total Request Value, Remaining Budget) and assigns an instant operational status (Approved or Budget Exceeded - Flagged).

Data Sanitization: Implements defensive coding logic to strip currency formatting and string artifacts, preventing data type mismatches during execution.

3. Executive Dashboard (Looker Studio): Connects to the processed sheet to visualize site-wise expenditure trends, top requisitioned materials, and budget variance metrics in real time.

## Key Features
Zero-Latency Ingestion: Requisitions are evaluated and processed the moment a form is submitted.

Automated Budget Enforcement: Prevents unmonitored over-budget purchases through programmatic flag logic.

Audit-Ready Data Integrity: Enforces structured validation, eliminating manual formatting discrepancies and transcription errors.

Scalable Architecture: Designed to seamlessly integrate additional field sites or modified BOQ structures with zero reconfiguration.

## Tech Stack
Language / Platform: JavaScript / Google Apps Script

Data Store: Google Sheets

Ingestion Layer: Google Forms

Visualization: Looker Studio (formerly Data Studio)
