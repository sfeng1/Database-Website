# Database Website, CS340_Final_project

## Summary

This is a mock small business website that interacts with the backend database to track marketing campaigns, products, inventory, transactions, and customers.
The database was a MariaDB instance provided by the university, likewise, the website was hosted by the university web server. 

This project is primarily designed to teach students about good database design and implementation practices. 

For a full brief on the project, including its functionality, implementation details, sample data, and queries, see the **summary.pdf** file included in the repo. 

## Project Overview

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

## Database ERD

![1](https://github.com/sfeng1/Database-Website/assets/114194642/cebf363b-3d92-4258-8bef-239582b4fdd7)

## Citations:
https://github.com/osu-cs340-ecampus/flask-starter-app
08/03/2023
flask-starter-app
[Source code]     
