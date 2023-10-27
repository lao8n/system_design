**Denormalization**

Process of restructuring data to reduce data redundancy and improve read performance often at the cost of increased write complexity and storage. 

Examples
* Embedding e.g. address details in another database
* Materialized views e.g. maintain multiple data views for different query patterns
* Pre-aggregated data e.g. for columnar databases 
* Pre-filtered data e.g. read and unread separate tables for emails rather than filtering 