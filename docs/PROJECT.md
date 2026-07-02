# Tanmay ERP

**Project Specification (PROJECT.md)**

Version: 1.0 (Draft)

## Vision

Tanmay ERP is a custom ERP system designed specifically for a wedding
card manufacturing business.

## Core Philosophy

-   PostgreSQL is the master database.
-   Google Sheets is the reporting layer.
-   Google Drive stores uploaded documents.
-   Every uploaded document must be verified before posting.
-   Every important action is audited.

## Customer Rules

-   Customer uniqueness = Customer Name + City.
-   Store only Customer Name and City in Customer Master.

## Product Rules

-   SKU
-   Card Name
-   Paper Size 1 + Qty/Set
-   Paper Size 2 + Qty/Set (optional)
-   Packing Standard

## Order Rules

-   Order ID comes from customer order forms.
-   One order can contain multiple products.
-   One order may be fulfilled through multiple dispatches.
-   Orders can be manually marked Fulfilled.

## Dispatch Rules

-   Dispatch ID comes from sales vouchers.
-   One sales voucher belongs to one customer.
-   One sales voucher may fulfill multiple orders and products.

## Inventory Rule

Finished Stock = Manufactured − Dispatched

## AI Workflow

Upload → Extract → Draft → Verify → Post to PostgreSQL → Sync Google
Sheets → Audit

## Goal

Build an AI-first ERP tailored for the wedding card manufacturing
business.
