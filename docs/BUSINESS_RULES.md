# BUSINESS_RULES

## Customer

-   Unique customer = Customer Name + City.
-   Store only Customer Name and City.

## Orders

-   Order ID comes from order form.
-   One order contains multiple products.
-   One order can be fulfilled by multiple dispatches.
-   Orders may be manually marked Fulfilled.

## Dispatch

-   Dispatch ID comes from sales voucher.
-   One sales voucher belongs to one customer.
-   One sales voucher may fulfill multiple orders.
-   One sales voucher may contain multiple products.

## Manufacturing

-   Production Report Number is auto-generated.

## Inventory

-   Available Stock = Manufactured - Dispatched.

## AI

-   Every uploaded document requires user verification before posting.
