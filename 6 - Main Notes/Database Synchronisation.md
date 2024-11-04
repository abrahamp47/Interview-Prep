2024-10-28 19:14

Status:

Tags:

# Database Synchronisation

Create a system for synchronisation two Databases that may not have the same schema, some table can be 1:1 mapping but others could be different.

Non-functional 

1.Eventual Consistency
2.cross synchronisation
3.Conflict resolution
4.Only update and insert
5.we cant use CDC processing tool because it disturbs the existing setup. Must perform cdc non invasively

Mapping/Transformation config 

Changes made -> fed to MQ system -> Transformation Engine 

Usecase - Migration from Monolith to Microservices

Service No 1

We use a service view the changes in the databases and feed it to kafka, for eg in MsSQL every table has a CDC table. Service see if the timestamp changed, if it changed then feed it to kafka.

Service 2
Transforms according to the mappign rules/config, then Update or Insert service takes the transformed data and makes the changes on the DB accordingly

Service 2

one sql table to store mapping

id
Source table
Target table
Transformation Fn:


DB Details

DbId
DbConnectionString
DbHash


Scaling -
Just scale service 2 and make them read from kafka queue to avoid duplication

How to increase consistency when its down(Cassandra Consensus)

Reading thing bottleneck, (similar to Redis)




# References


