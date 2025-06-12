# 2024-06-12 Readjustment of Tables - DB Modeling

## What I did today
- Readjusted the tables from logical DB modeling
- Prepared documentation for an upcoming presentation
- Conducted data tests using Excel and MySQL

## What I learned
- Before moving on to the physical modeling stage, we held a final team meeting to review and analyze each table. During this session, we discussed how to handle refunds and returned products, and which domain should be responsible for this logic.
- Previously, refund processing was handled within the payment domain, but after additional research and feedback, we concluded that refund management should belong to the order domain.
- Based on this, we added two separate tables to the order domain:  
    1) a table for managing each individual refund/exchange request  
    2) a table for managing the history of refund/exchange status changes.
- This approach separates these records from the existing order history table, helping to prevent data overload and enabling more granular management by order item. As a result, it is now possible to support partial refunds, exchanges, and cancellations at the item level.

## Goals for tomorrow
- Deliver a presentation on the modeling process and results
- Peer review: review other teams’ work
