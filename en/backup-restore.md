## Database > RDS for SQL Server > Backup and Restoration

## Backups

It is available to prepare for restoring database of a database instance. RDS for SQL Servers helps to back up the entire database instance, not an individual database. 
Backups can be manually created at a time of choice or automatically created by setting backup retention period. 
Restoration is available to a particular time by using manually created backups, or to a point of time during backup retention period. 

> [Caution]
> While backup is underway, performance may be degraded due to such backup.  
> To minimize the impact on service, backup is recommened while service workload is low.

### Backup Storage 

RDS for SQL Server helps to store all backup files at a backup storage. Backup storage is provided free of charges, as much as the sum of storage size of all database instances of a region, while the exceeding part shall be charged.  
Auto backup files are deleted along with database instance deletion, while manual backup files are permanently saved at a backup storage, unless specified otherwise by user.  

### Auto Backup

By setting up the backup retention period for more than a day, auto backup is enabled and executed during specified backup execution period. Unless the backup execution time is specified, daily auto backup shall be executed when there is the minimum workload. By specifying backup time, auto backup is executed within 15 minutes from the specified time. Auto backups can be saved for up to 30 days. When the backup retention period setting is N/A, auto backup is disabled, deleting all auto backup files saved from backup storage. With the auto backup disabled, restoration to a point of time during backup retention period becomes unavailable, while restoration to a particular time with manual backup only is available.   

### Manual Backup

Regardless of auto backup enabling, a backup to a time of choice can be manually executed. To create a manual backup, it must be named to meet the following rules:   

* Must be unique for each region.
* Must be comprised of alphabets, numbers, -, _ , and . only, between 4 and 100 characters. 
* Must start with a letter. 

## Restoration

RDS for SQL Server helps to restore to a backup moment by using backup files, or to a point in time. With restoration, a new database instance is created, which is irrelevant to an existing database instance. Since restored database instance regards to database only, a new setting of a parameter and a security group is required. Setting of a new parameter group is available, but it is recommended to restore with the parameter group from the backup time.    

### Restoration with Backup

수동 혹은 자동 백업을 이용하여 DB 인스턴스를 복원할 수 있습니다. 복원에 걸리는 시간은 백업의 크기에 따라 다르며, 수분에서 수십 분이 소요됩니다. 
복원할 DB 인스턴스의 타입과 파라미터 그룹은 백업할 당시의 DB 인스턴스와 동일하게 설정하는 것을 권장합니다. With manual or auto-backups, database instance can be restored. Restoration time depends on the backup size, from minutes up to dozones of minutes. It is recommended to apply the same type of database instance and parameter group 

### Restoration to a Point in Time during Backup Retention Period 

DB 인스턴스의 자동 백업이 활성화되어 있다면, 보관 기관 중 어느 한 시점으로 복원이 가능합니다. 시점 복원을 하기 위해서는 별도의 로그 백업이 필요합니다. RDS for SQL Server 는 매 5분마다 자동으로 로그 백업을 수행한 후, 백업 스토리지에 저장합니다. 자동 백업을 활성화 한 시각부터, 가장 최근 로그 백업을 저장한 시점까지 복원이 가능합니다. If auto backup is enabled for a database instance, it is available to restore data to a time point during retention period. To enable a point-in-time restoration, log backup is required. RDS for SQL Server executes auto log backups at every 5 minutes, and stores them at a backup storage. 
