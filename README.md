# MIST4610GroupProject1

TEAM NAME:
-------------------------
Sp24 21484 Group 3

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

(Data model would not fit in one picture clearly)

<img width="468" alt="model1" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/e30026fa-783b-44e8-a0e3-611a16a1d1f7">
<img width="468" alt="model2 2" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/a0c23cf3-57ae-4716-a676-b53d55f348b4">



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


<img width="618" alt="Screenshot 2024-03-27 at 5 53 00 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/956b31f7-e07e-4234-8c4a-2a9e09ff5d05">



Query 1:
List the client name, the loan amount, their interest rate on the loan, and the number of payments made by the client if their credit score is greater than the average credit score.

<img width="1143" alt="Screenshot 2024-03-27 at 5 46 46 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/c7739c27-fe4f-47d5-8701-a563da0f6624">

This query would be useful to management in order to see how many payments customers with a higher than average credit score have made. This can give them good data on how customers with higher than average credit make payments on their loans, and can use this information to further their risk management strategy when it comes to giving out loans.



Query 2:
List the client name, their monthly income, the loan amount, and the loan interest rate for each loan where the client does not have collateral.

<img width="1144" alt="Screenshot 2024-03-27 at 5 47 11 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/c4a5d156-f723-44a6-a8f5-e983ecbbe703">

This query would serve the purpose of showing all the loans from customers who did not have any collateral associated with their loan. Since the collateral data is separate from the loan table, there is no easy way to see which loans have collateral. This can show the unsecured loans the firm gives out. 



Query 3:
List the clientId, name, that has a good credit score and a low remaining balance to suggest that these clients are the ones doing well on their repayment and can be trusted.

<img width="1145" alt="Screenshot 2024-03-27 at 5 47 27 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/f45f14ee-d7bc-4e26-aa43-6954fc97f904">

Empower could use this query to view customers that have been doing well on their repayment plans that have a good credit score. This can show them that these loans are safe bets to be paid off in the near future. This shows them where they stand and how they will profit in the near future when these customers repay their loans.



Query 4:
List the Client name (In one column), credit score, interest rate, loan amount for accounts with an active status. List the results in descending credit score amount.

<img width="1144" alt="Screenshot 2024-03-27 at 5 47 45 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/f83a9d92-a9af-46fd-9bdc-eac0e71e18a4">

This query helps the bank identify loans that are most likely to be repaid by customers with active accounts. This valuable insight enables the bank to assess the least risky loans and to set appropriate interest rates for future loans with specific customers. This will make their loan interest rates more accurate in the future so they can ensure customers are treated fairly and will want to pay back their loans.



Query 5: 
List the loanAmount and Estiamted Collateral Value for Loans with a poor credit score, a poor credit score is anything below 550.

<img width="1146" alt="Screenshot 2024-03-27 at 5 48 06 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/fb985e1f-d59b-452e-9b07-dbcfa0c9afeb">

This query identifies loans that are at a high risk of default based on customers' credit scores. This information allows the bank to estimate potential gains or losses from defaults by considering the collateral value of these loans. Furthermore, the bank can conduct further risk assessments to their clientele and see which loans should require some form of collateral. 



Query 6:
List each industry and calcualte the total remaining loan balance for each industry.

<img width="1145" alt="Screenshot 2024-03-27 at 5 48 22 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/b9f4b484-1392-43dd-bcf1-34c912dfef90">

This query calculates the remaining loan balance for each industry to which the bank has lent money. This information is crucial for the bank to assess the financial health of various industries, which can significantly impact the probability of loan repayments. They can also then determine which industries are the most risky and least risky to give out loans to.



Query 7:
Select information about loans that already been approved, have a remaining balance under $5000, an active item in collateral, and originated from the branch 'Fliptune'. Include info about the employee that issued the loan, and the branch that the employee works in.

<img width="1144" alt="Screenshot 2024-03-27 at 5 48 39 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/2c5eeca3-0244-4441-85c8-0e26b8e469c8">

This is an example query Empower can use that shows the specificity of the database. This information will be useful, especially as more data is entered, in the sense that it can track individual loans that come from certain branches. The company can also reach out to the employee to gain a status update on how the loan repayment is coming along.



Query 8:
List all loan officers along with the name of the branch they belong to and the count of loan applications they have processed in descending order.

<img width="1144" alt="Screenshot 2024-03-27 at 5 48 53 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/0d6a03a1-7d52-42e7-9a90-cbe66b9ce2ae">

This query allows us to see the performance of each loan officer based on the number of loan applications they have processed. The results of this query may help establish which loan officers and branches are most productive, allowing the owner(s) of the micro-loan provider to assess ways in which to improve efficiency.



Query 9:
List all clients along with the amount of all of the payments they have made.

<img width="1145" alt="Screenshot 2024-03-27 at 5 49 12 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/bbf00932-c450-4084-bceb-ff2484805de2">

This query allows us to view all of the clients and the amount of all of the payments they have made, which helps monitor client payment behavior and analyze payment history to assess management and risk associated with clients. Additionally, it can show how much each client has paid on their loan and track the progress of that.



Query 10:
List the first and last name of the Loan Officers, the number of loans they've been assigned to, and the average loan amount for those loans where the loan amount is greater than the average loan amount for all loans.

<img width="1142" alt="Screenshot 2024-03-27 at 5 49 31 PM" src="https://github.com/brendanr14/MIST4610GroupProject1/assets/149964823/b20303e8-ae53-471f-9c56-e302c8ea23cc">

This query allows us to see the number of loans that Loan Officers have been assigned to that is above the average for the company as well as the loan amounts which are above average. This may help establish how much work Loan Officers are being assigned and the severity of the Loans still owed.







DATABASE INFORMATION:
-------
Name of attributed Database: ns_Sp24_21484_Group3

Additional Information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Qx;
