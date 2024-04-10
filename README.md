# Database Website, CS340_Final_project

# Summary

This is a mock business website that interacts with the backend database to track marketing campaigns, inventory, transactions, and customers.
The database was a MariaDB database provided by the university, likewise the website was hosted by the university web server. 

Thie project is primarily designed to help students display and practice good database design and implementation practices. 

# Project Outline

Whitney is a small business owner of The Bamboo Closet which sells Ie-dyed silk fans and other Ie-dyed
products. Each month, she sells approximately 200 products. She also invests in social media adverIsing,
which she believes boosts her sales. Whitney is interested in determining which products sell the best
and fastest, as well as whether there is a direct correlaIon between the sales of certain products and the
money spent on adverIsing them. Whitney is also interested in how o_en there are repeat customers.
This informaIon will enable Whitney to make more informed business decisions regarding stock
quantites and the effeciveness of adverisements.

The goal of this database is to provide data for Whitney to make important business decisions. For
determining which products sell the most we can look at the Sales table. To see which products sell the
fastest, we can look at the date an item was put into inventory compared to the date it was sold on the
sales table. For informaIon on the effecIveness of money spent on adverIsing we can look at the
campaigns table and look for a correlaIon between the sale dates and the campaign dates. For
informaIon on repeat customers, we have a calculaIon a-ribute in the customers table that calculates
how many separate Imes a customer has made a purchase. 

# Database Outline

Database Outline
Calculated fields are green and show up on the website via read funcIon, but aren’t in the database.
• Customers: Records the details of each customer products are sold to.
o Attributes:
§ customerID: int, autoincrement, unique, not NULL, PK
§ customerName: varchar, not NULL
§ customerEmail: varchar
§ totalRevenue (calculation based on sum of sales): decimal (19,2)
§ salesCount (calculation based on count of sales for this customer): Int
o Relationships:
§ 1 to M with Sales: each customer can have multiple sales
• Products: Table of all available products
o Attributes:
§ productID: int, autoincrement, unique, not NULL, PK
§ productName: varchar, not NULL
§ productPrice: Decimal (19,2), not NULL
o Relationships:
§ 1 to M with SaleItems: intersection table to facilitate M:M relationship with
Sales table
§ 1 to M with Inventory: each product can have multiple inventory entries to
reflect inventory added on different days
§ 1 to M with Campaigns: intersection table to facilitate M:M relationship with
Channels table
§ Channels: Influencers on social media that are paid to promote a product
• Channels: Influencers on social media that are paid to promote a product
o Attributes:
§ channelID: int, autoincrement, unique, not NULL, PK
§ channelName: varchar, not NULL
§ channelEmail: varchar, not NULL
§ rate: decimal (19,2), not NULL (this is a daily rate)
o Relationships:
§ 1 to M with Campaigns: intersection table to facilitate M:M relationship with
Products table
• Campaigns (intersection table):
o Attributes:
§ campaignID: int, autoincrement, unique, not NULL, PK
§ channelID: int, FK
§ startDate: date, not NULL
§ endDate: date,
§ productID: int, FK
§ cost: decimal (19,2) (calculation based on channel.rate*length of campaign)
o Relationships:
§ M to 1 with Channels: each channel can run multiple campaigns
§ M to 1 with Products: a product can have multiple influencer campaigns
• Sales: list of all sales The Bamboo Closet has made
o Attributes:
§ saleID: int, autoincrement, unique, not NULL, PK
§ customerID: int, FK
§ saleDate: Date, not NULL
§ totalSaleValue (calculation based on sum of lineItemCost from saleItem):
decimal (19,2)
o Relationships:
§ M to 1 with Customers: each customer can have multiple sales
§ 1 to M with SaleItems: intersection table to facilitate M:M relationship with
products
• SaleItems (intersection table): details of an individual sale
o Attributes:
§ saleItemID: int, autoincrement, unique, not NULL, PK
§ saleID: int, FK
§ productID: int, FK
§ quantity: int, not NULL
§ totalLineItemCost (calculation of productID.productPrice * saleQuantity):
decimal (19,2)
o Relationships:
§ M to 1 with Products: a product can be associated with multiple SaleItems
§ M to 1 with Sales: a sale can have multiple SalesItems
• Inventory: list of products that are currently available for sale and their quantities
o Attributes:
§ inventoryID: int, autoincrement, unique, not NULL, PK
§ productID: int, FK
§ dateAdded: date, not NULL
§ quantity: int, not NULL
§ totalValue (calculation based on quantity * productID.productPrice: decimal
(19,2)
o Relationships
§ 1 to M with Products: A product can have m


Citations:
https://github.com/osu-cs340-ecampus/flask-starter-app
08/03/2023
flask-starter-app
[Source code]     
