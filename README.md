Link For Code Repository - https://github.com/vinays0409/nagp-kubernetes

Service tier - Docker Hub Image URL - https://hub.docker.com/r/vinay0409/nagp-api
Database tier - Docker Hub Image URL - https://hub.docker.com/_/postgres

URL for Service API tier to view the records from backend tier - http://34.122.126.89/items
Note: The above mentioned url uses the external endpoint for Service tier Loadbalancer service. If it does not work its because the cluster is stopped on GCP. Kindly contact me in case required.

How to populate the database with initial data:
There are two following ways in which database can be populated with initial data

1. Using a convenience API endpoint created for this assignment in Service tier which can be run onced to populate the Database.
   This requires both the database and service tier to be deployed. This also used the external endpoint for Service tier Loadbalancer service.
   http://34.122.126.89/populatedb

2. After the database deployment is done run the following commands from the cloud shell inside the cluster:

   kubectl exec -it db-stateful-0 -- bash

   psql -U vinay -d nagp-db -c "
   CREATE TABLE items (
   id SERIAL PRIMARY KEY,
   name VARCHAR(255),
   price DECIMAL(10, 2)
   );
   INSERT INTO items (name, price)
   VALUES
   ('Item 1', 3.99),
   ('Item 2', 4.99),
   ('Item 3', 5.99),
   ('Item 4', 1.99),
   ('Item 5', 2.99),
   ('Item 6', 7.99),
   ('Item 7', 8.99),
   ('Item 8', 9.99),
   ('Item 9', 1.99),
   ('Item 10', 6.99);
   "
