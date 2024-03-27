# MIST4610GroupProject1

TEAM NAME:
-------------------------
21484 Group 3

TEAM MEMBERS:
-------------------------
1. Brendan Rice | [@brendanr14](https://github.com/brendanr14/MIST4610GroupProject1)
2. Roshan Maganti | [@rmaganti6](https://github.com/RMAGANTI6/MIST4610GroupProject1)
3. Areez Shaikh | [@areezshaikh](https://github.com/areezshaikh/MIST4610GroupProject1)
4. Jack Gannon | [@jackgannonn](https://github.com/JackGannonn/MIST4610GroupProject1)
5. Brayden Keller | [@braydok12](https://github.com/braydok12/MIST4610GroupProject1)
6. Ella Gunning | [@ellagunning](https://github.com/ellagunning/MIST4610GroupProject1)

PROBLEM DESCRIPTION:
-------------------------
Situation: Pretend you are the owner/operator of a micro-loan provider needing to build a relational database. You hired some students from the MIST 4610 class at the University of Georgia to create the database for you. They need to know more about your organization to identify which entities, attributes, and relationships are important for you. Start by describing your business as a real client

We were tasked to create a relational database for micro-loan provider Empower Microfinance Solutions. They offer different kinds of loans to various clients, which are tracked through the various entities described below. They also wanted to track different components of their firm internally, such as the different employees and branches. We wanted to accurately portray the relationships between these entities, as well as populate each table with data that Empower can use to gain further insights into their clients, loans, and employees. Additionally, we wrote 10 sample queries for our client to show the functionality, usability, and power of the database we created and how they could further use it to advance their business objectives.

DATA MODEL:
------------------------
Our model fits the needs communicated to us by Empower Microfinance Solutions. One of the more important and all encompassing entities is the Client table. This entity includes all relevant attributes Empower would want to know about each client, including an identifying client number, their name, address, and income, among others. This table is related to various other tables. There is a one-to-one relationship between Client and CreditScore, as each client has just one credit score. Another one-to-one relationship exists in the form of Client and ClientAccount. The ClientAccount table allows Empower to accurately identify a client from their account, and vice versa. There is a one-to-many relationship between Client and LoanApplication, as one client can submit many loan applications. Lastly for Client, there is a one-to-many relationship to Loan. Each client may have multiple active loans, and having this relationship is paramount to tracking which clients are responsible for which loans.

At the center of the data model is the Loan entity. This tracks essential information about each loan given out by Empower, such as the amount, interest rate, remaining balance, and others. In addition to relationship previously explained with Client, there are many other important relationships to note for this table. There are one-to-one relationships from Loan to LoanApplication and Collateral. Each loan only has one loan application, and Empower only allows for one source of collateral from each client. As the Loan and Client table are related, Empower will be able to track each collateral item to a specific client through the use of foreign keys.

The Loan entity is also related to other entities, such as Payment and Transaction. These entities differ as Payment only tracks client payments on their loans, while Transaction captures data about various financial activities Empower engages in such as fees or account adjustments. Both of these tables have a one-to-many relationship to Loan, as each loan can have multiple payments and multiple transactions during its lifetime. Along with these tables, Loan is also related to the FinancialProduct entity. Each financial product is  used in many loans, and is a way for Empower to maintain consistency among the different loan products they offer to clients. Lastly for Loan is LoanOfficer in a one-to-many fashion. Each loan officer can be assigned to many loans at once, and this table tracks relevant information about the loan officer such as their name, phone, and job title. 

From LoanOfficer, we switch to a more internal focus on the databse. LoanOfficer is related to the Branch table with a one-to-many relationship. Each branch has many loan officers, but a loan officer only belongs to one branch of the company. This relationship can also help us track information about branch success when it comes to loans through the use of foreign keys. Finally is the Employee table, which tracks all other kinds of employees that work for Empower. This has a one-to-many relationship with Branch, as each branch has many employees, but an employee may only belong to one branch. 

DATA DICTIONARY:
---------------------
Table: Branch

<img width="321" alt="Screenshot 2024-03-26 at 8 51 30 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/d03faa0e-3219-445e-8ffd-5f14a1a8a05e">


Table: Client

<img width="316" alt="Screenshot 2024-03-26 at 8 41 22 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/2199e547-8d73-4007-a25f-9761e6899557">


Table: ClientAccount

<img width="316" alt="Screenshot 2024-03-26 at 8 48 32 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/1c308af9-ea13-4244-bba7-18665f3e4c90">


Table: Collateral

<img width="341" alt="Screenshot 2024-03-26 at 8 52 48 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/3462a4d2-b4c7-4046-985a-c8567d7b0a54">


Table: CreditScore

<img width="329" alt="Screenshot 2024-03-26 at 8 35 59 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/d0c6b703-416a-448c-a037-a504528afc63">


Table: Employee

<img width="323" alt="Screenshot 2024-03-26 at 8 52 01 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/38018911-352b-40ab-9407-4b0b7827e83f">


Table: FinancialProduct

<img width="315" alt="Screenshot 2024-03-26 at 8 50 39 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/f635205a-ccd4-4f57-988b-345700f67863">


Table: Loan

<img width="315" alt="Screenshot 2024-03-26 at 8 49 17 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/cba59cc6-7444-4c4a-8ee0-8e1e388b9a75">


Table: LoanApplication

<img width="314" alt="Screenshot 2024-03-26 at 8 42 57 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/f8a331a3-4626-4c66-a90d-ed72d37f9508">


Table: LoanOfficer

<img width="314" alt="Screenshot 2024-03-26 at 8 51 09 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/daa694c2-e62d-4602-a03d-3fd3218ab604">


Table: Payment

<img width="328" alt="Screenshot 2024-03-26 at 8 53 05 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/0f4c668a-b929-4d61-ad4c-a4b727a85436">


Table: Transaction

<img width="322" alt="Screenshot 2024-03-26 at 8 52 21 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/651cf481-1913-402e-bb92-91436a3f5548">



QUERIES:
-----------


DATABASE INFORMATION:
-------
Name of attributed Database: ns_Sp24_21484

Additional Information: Each query listed above is marked in the database using stored procedures which can be called using the following format: ____
