## Database > RDS for SQL Server > Database Instance

Database instance encompasses virtual equipment and installed Microsoft SQL Server, serving as the unit of Microsoft SQL Server provided by RDS for SQL Server. 
Direct access to a database instance is not allowed, but access is enabled only through the port entered when creating the database instance. 
Database instances can be identified by user-specified name or automatically assigned 32-bit ID. 
A database instance must be named, considering the following constraints: 

* Must be unique for each region. 
* Must be comprised of alphabets, numbers, -, _ ,and .only, between 4 and 100 characters.
* Must start with a letter. 

To create a database instance, user account and password setting is required, considering the following constraints: 

* User account must be between 4 and 16 characters, comprised of alphabets and numbers only, starting with a letter. 
* Password must be between 8 and 128, comprised of alphabets, numbers, !, $, #, and % only. 
* Password cannot include user's account name. 
* Password must include at least three categories out of capital letters, small-case letters, numbers, and special characters. 

### Availability Area

RDS for SQL Server has many availability areas under one system so as to prepare against failure in physical hardware. A failure occurred within an availability area does not affect other availability areas, raising availability of the entire service. Database instances that are dispersed and created in different areas can communicate via network, with no charges.   

> [Caution]
> The availability area of already-created database instance cannot be changed. 

### Version of Microsoft SQL Server

Only the SQL Server 2016 Standard version is supported.   

### Database Instance Type

Each type of database instance has different CPU core count and memory volume. 
To create a database instance, an appropriate type must be selected depending on the database workload. 



| Type    | Description |
| ------- | -------------------------------------------------|
| m2 | Configures balance between CPU and memory.   |
| c2 | Has higher performance setting for CPU. |
| r2 | Available when momory takes more volume than other reources|

It is easy to change the type of already-created database instance via web console.

> [Caution]
> Changing already-created database instance type requires minutes of downtime since database instance must be closed. 

### Storage Type

Database instances support two storage types: HDD or SSD. 
Since each storage type provides different performance and pricing, an appropriate storage type must be selected depending on the database workload.  
A storage type can be created from 20GB up to 2,000 GB. 
It is easy to change the size of already-created storage via web console. 

> [Caution]
> Changing already-created storage size requires minutes of downtime since database instance must be closed. 
> The type of already-created storage cannot be changed. 

## High Availability DB Instance

RDS for MS-SQL provides the high availability feature by using the mirroring feature of the Microsoft SQL Server database that has the primary server, secondary sever and monitoring server. The primary server and the secondary server are created in different availability areas.

### Failover action 

A failover action automatically takes place when the primary server becomes unavailable due to an unexpected failure. Upon failover, the failed primary server is halted to prevent split brain and the secondary server takes over the primary server. Applications do not have to be adjusted for this change, as the A record of the internal and external domains that are used to connect is automatically switched from the primary server to the secondary server.
When failover is complete, high availability DB instances will disappear and the rest of DB instances are separated into two groups: the failed DB instances and the DB instances promoted due to the failure. The promoted DB instances inherit all the configurations of existing DB instances except backups. The promoted DB instances will not perform backed up immediately after the promotion. This is to prevent any system load after the failover action.
DB instances with failover completed can be restarted using the [Restart] button.

### Manual failover action

A high availability DB instance can be manually restarted after the failover action to deal with failover. When restarting a DB instance using failover, manual failover is performed and the roles of the primary and secondary servers are switched. During failover, both primary and secondary servers will restart their Microsoft SQL Server process and their internal and external domain IPs will be changed. Connection to those servers may fail from a couple of seconds to a couple of minutes until the domains are successfully changed. When failover is complete, the system automatically performs a backup.
