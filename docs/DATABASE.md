# DATABASE.md

## Tanmay ERP Database Specification

**Version:** 1.0 (Draft)

### Database

-   PostgreSQL
-   UUID primary keys
-   UTF-8
-   Asia/Kolkata timezone

### Tables

#### customer

-   id
-   customer_name
-   city
-   created_at
-   updated_at
-   UNIQUE(customer_name, city)

#### product

-   id
-   sku
-   card_name
-   packing_standard
-   active

#### product_paper

-   id
-   product_id
-   paper_size
-   quantity_per_set
-   unit

#### order

-   id
-   order_number
-   customer_id
-   order_date
-   remarks
-   status
-   fulfilled_manually

#### order_item

-   id
-   order_id
-   product_id
-   ordered_quantity
-   dispatched_quantity
-   status

#### production_report

-   id
-   production_report_number
-   production_date
-   remarks

#### production_item

-   id
-   production_report_id
-   product_id
-   quantity

#### dispatch

-   id
-   dispatch_number
-   customer_id
-   dispatch_date
-   remarks

#### dispatch_item

-   id
-   dispatch_id
-   order_item_id
-   product_id
-   quantity

#### customer_ledger

-   id
-   customer_id
-   voucher_number
-   transaction_type
-   debit
-   credit

#### document

-   id
-   document_type
-   google_drive_file_id
-   ai_extracted_json
-   verified_json
-   status

#### audit_log

-   id
-   table_name
-   record_id
-   action
-   old_value
-   new_value
-   performed_at

### Views

-   vw_inventory
-   vw_pending_orders
-   vw_customer_balance
-   vw_paper_requirement
-   vw_dashboard

### Business Rules

-   Customer uniqueness = Customer Name + City
-   One order contains multiple items
-   One order -\> many dispatches
-   One dispatch -\> one customer
-   One dispatch -\> many orders
-   Inventory = Manufactured - Dispatched
-   Order IDs come from order forms
-   Dispatch IDs come from sales vouchers
-   Production report numbers are auto-generated
-   User verification required before posting AI-extracted documents.
