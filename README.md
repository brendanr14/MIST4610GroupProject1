# MIST4610GroupProject1

TEAM NAME:
-------------------------
21484 Group 3

TEAM MEMBERS:
-------------------------
1. Brendan Rice | [@brendanr14](https://github.com/brendanr14/MIST4610GroupProject1)
2. Roshan Maganti
3. Areez Shaikh | [@areezshaikh](https://github.com/areezshaikh/MIST4610)
4. Jack Gannon
5. Brayden Keller
6. Ella Gunning

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


QUERIES:
-----------


DATABASE INFORMATION:
-------
