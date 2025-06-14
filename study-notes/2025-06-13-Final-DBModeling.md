# 2025-06-13 Final Step of Logical DB Modeling

## What I did today
- Gave a final presentation on our database modeling project
- Reflected on new approaches and ideas through peer review and by attending other teams’ presentations
- Studied paging functionality in a Spring Boot course

## What I learned

### 🧾 Order-Related Tables

#### Order Creation and Storage
- When an order is placed, overall order information is stored in the `Order` table.
- Details for each product within the order are saved in the `OrderDetail` table.

#### Order Status Change History Management
- When the order status changes, the new status is updated with a reference to the `OrderStatusCode` table.
- All changes are logged in the `OrderHistory` table for tracking purposes.

#### Handling Cancellations, Returns, and Exchanges
- Refund, return, and exchange requests are recorded in the `RefundReturn` table.
  - This structure supports partial refunds and partial exchanges.
- Each step and status change in the processing flow is tracked in the `RefundReturnHistory` table.

#### Comprehensive Tracking and Audit Trail
- All events and status changes related to orders, shipping, cancellations, returns, and exchanges are fully recorded and traceable through detailed tables and their corresponding history tables.

![image](https://github.com/user-attachments/assets/c3fdd9f0-8407-42ac-8e05-3eb90c975c41)

- Although I spent a lot of time thinking through this structure, listening to other teams’ presentations and participating in peer reviews made me question whether my approach was optimal.
- I especially struggled with the design of refunds and exchanges. I chose to manage both the current status and the change history in separate tables, but some teams separated refunds and exchanges into distinct domains.
- I plan to further refine this part of the model, and will review additional constraints that may be necessary.

---

### Reflections

Through this project, I was able to gain a much deeper understanding of concepts that previously felt abstract when studied only in theory.  
By designing the ERD and thinking through the actual business processes, I learned firsthand where to store information and how to reference it efficiently.  
I realized the importance of design—how all core entities are connected and that defining these relationships is both complex and critical.  
Although each team member was responsible for different entities, the entire process was interconnected, and this highlighted the need for effective communication and collaboration within the team.  
Moving forward, I will continue to pay close attention to the importance of design and aim to approach it even more carefully and thoroughly.

## Goals for tomorrow
- Study how to implement the "read" (view) function for the message board
- Add and refine modeling constraints
