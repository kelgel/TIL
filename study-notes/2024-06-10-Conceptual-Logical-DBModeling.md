# 2024-06-10 Conceptual & Logical DB Modeling

## What I did today
- Through conceptual modeling, identified key subject areas and defined core entities.
- Modeled the Order entity using the ERD Cloud tool.
- Studied the logical database modeling chapter of a database modeling textbook.
- Engaged in frequent team meetings for effective communication and collaboration.

## What I learned

- The steps of database modeling, especially conceptual and logical modeling:
    - Conceptual Modeling:          
      - Purpose: To suggest a high-level data model based on the purpose and direction established during the data analysis process, viewed from a broad perspective.
      - Three Main Concepts:   
        1. Derive subject areas.    
        2. Differentiate and define subject areas.    
        3. Define key entities and their relationships.    

  - Logical Modeling:     
      - Purpose: To define the data required for business operations in a clear and concrete manner.     
      - Four Standards for key entity   
        1. Type & Category
        2. Rule & Knowledge
        3. Subject & Object
        4. Where (Location/Context)

- How to Extract key entity and detailed attributes
    - *Self driven questions during modeling*    
        - Q.  Should product options, quantity, and actual purchase price be saved in the order detail table, even if this information is also in the product table?         
           A. Yes.    
           → Reasoning: Product information (options, prices) can change over time.  
             The "option/size/quantity/price" at the time of order placement must be historically preserved.   
             Without saving this historical data, it would be impossible to accurately recreate past orders if product details change later.     
             This is crucial for accounting, customer inquiries, and customer service.   
          
        - Q. Should the order and order detail tables be separated or integrated?      
            A. Separated.   
            → Reasoning: A single order can contain multiple products, and different products within the same order may have distinct conditions or attributes.
              Separating them allows for more flexible and normalized data representation.    
    
- The importance of frequent team meetings for communication and collaboration
    - *Why it matters:*    
      - Frequent meetings facilitate early issue resolution, goal alignment, and foster stronger working relationships within the team.    
      - By holding regular meetings throughout the modeling process, teams can prevent the creation of redundant tables and unnecessary tasks, leading to a more efficient and accurate database design.    

## Goals for tomorrow
- Conduct a peer review of the modeling work and revise as needed.   
- Progress to the next step: physical modeling.  
