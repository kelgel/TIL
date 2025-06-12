# 2025-06-11 Logical DB Modeling Improvement

## What I did today
- Conducted peer review and received feedback from my instructor
- Revised and improved the database tables based on the feedback   

## What I learned

- The precise concept of logical modeling (based on feedback)
    - Instead of simply storing all information in a table, consider which data should be displayed and where.
    - When designing the logical model and specifying table attributes, it's important to focus only on the attributes truly needed for the “Order” table. For example, attributes like payment method or shipping address do not need to be stored in the Order table if they already exist in the Payment or Shipping tables and are linked by a foreign key (e.g., order_id). These values can be retrieved later via JOIN operations.
    - Only include attributes essential to the order entity itself; reference-related information through table relationships when necessary.    
---
- How to represent relationships between tables and design product option structures
    - Although I was responsible for the order domain, I needed a product option table, which was not provided by the product team. Therefore, I designed the product option tables myself, using a hierarchical structure (Large-Medium-Small categories).
    - Below is the table structure for implementing product options using a 3-level hierarchy:

### Option Table Structure

#### 1. Option Group Table (Large Category)

| option_group_id | group_name |
|-----------------|------------|
| 1               | Color      |
| 2               | Scent      |
| 3               | Volume     |

- **Description**: Defines the main option groups, such as Color, Scent, and Volume.  
- **Relationship**: Each group can have multiple subcategories (1:N with option_category).



#### 2. Option Category Table (Medium Category)

| option_category | option_group_id | option_category_name |
|-----------------|----------------|---------------------|
| 10              | 1              | Red Series          |
| 11              | 1              | Blue Series         |
| 12              | 2              | Floral Type         |
| 13              | 3              | Large Volume        |

- **Description**: Manages subcategories within each option group.  
- **Relationship**: Each group can have multiple categories (option_group 1:N option_category).



#### 3. Option Value Table (Small Category)

| option_value_id | option_category | option_value_name |
|-----------------|----------------|------------------|
| 100             | 10             | Burgundy         |
| 101             | 12             | Rose             |

- **Description**: Stores the most detailed option values (e.g., Burgundy under Red Series, Rose under Floral Type).  
- **Relationship**: Each category can have multiple option values (option_category 1:N option_value).



#### 4. Product Option Mapping Table

| product_id | option_value_id |
|------------|----------------|
| 10001      | 100            |

- **Description**: Maps products to their specific option values.  
  For example, product ID 10001 is associated with the "Burgundy" color option (full path: Color > Red Series > Burgundy).



- **Summary**:  
  The product option system is organized in a three-level hierarchy:  
  **Option Group (Large) → Option Category (Medium) → Option Value (Small)**.  
  This model allows for flexible and scalable management of diverse product options by linking products to detailed option values.

---
#### Why SKU Is Essential in E-commerce DB Design
While the above option tables are well-suited for classifying and managing individual product options, they are not sufficient for handling key business requirements such as inventory management, price variations, and out-of-stock status—especially when multiple options must be combined.
To address these challenges, it is crucial to introduce the concept of SKU (Stock Keeping Unit) and manage option combinations at the SKU level.

#### What Is an SKU (Stock Keeping Unit)?
An SKU (Stock Keeping Unit) is the smallest unit of inventory tracking in retail and e-commerce.
It represents a unique, sellable version of a product, defined by a specific combination of options (such as color, size, scent, etc.).
Each SKU is identified by a unique code (SKU code) and is used to track inventory, price, stock status, and sales history at a granular level.

#### Key Characteristics:

- Uniqueness:
Each SKU represents a unique combination of product options.
For example, “T-shirt / Red / Large” and “T-shirt / Blue / Large” are two different SKUs, even if they are variants of the same product.

- Smallest Unit for Inventory Management:
All inventory operations—stock counting, receiving, shipping, and out-of-stock detection—are performed at the SKU level.

- Sales Unit:
The SKU is what the customer ultimately selects and purchases. All sales, discounts, and promotions apply at the SKU level.

- Internal Management:
SKUs are used internally for inventory, logistics, and sales systems.
They are not always identical to customer-facing barcodes (UPC/EAN).

#### Advantages of Using SKUs
Advantage	Explanation
Precise Inventory Control	Enables accurate tracking of stock for every option combination (prevents overselling/stockouts)
Flexible Pricing	Allows different prices and promotions for different option combinations (e.g., “Red/XL” may cost more)
Stock Status Management	Out-of-stock or limited-stock status can be managed per SKU, not just per product or option
Efficient Order Processing	Supports fast and accurate picking/packing, since each order line maps to a specific SKU
Improved Analytics	Enables analysis of sales trends by variant (e.g., which color/size is most popular)
Scalability	Supports future expansion of product variants or new options without complex changes to the DB

---
- Types of History Management
    - There are two main types of history management: **Point-in-Time (Event-based) History** and **Period (Interval-based) History**.
    - **Order history management** uses point-in-time history.

### History Management Types

| Type                          | Description                                                                                           | Advantages                                        | Disadvantages                              |
|-------------------------------|-------------------------------------------------------------------------------------------------------|--------------------------------------------------|--------------------------------------------|
| Point-in-Time (Event-based)   | Only the change (event) time is recorded. Tracks the state at each event occurrence.                  | Simple data management; less prone to errors      | Hard to query the state at an arbitrary time |
|                               | E.g., Only records the timestamp when a change occurs                                                 | Easy to add new records                          | Inefficient for tracking status changes over time |
| Period (Interval-based)       | Records both the start and end times of each state (duration/period tracked).                        | Easy to query past states or periods             | More storage needed; requires consistency checks |
|                               | E.g., Each record has a start date and end date; suitable for tracking historical statuses            | Good for historical data analysis                | Incorrect data management possible if periods overlap or are missing |
|                               |                                                                                                       |                                                  | Users must be familiar with period-based systems |

---

## Goals for tomorrow
- Finish the logical modeling 
- Conduct the physical modeling using MySQL
