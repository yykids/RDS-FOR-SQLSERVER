## Database > RDS for SQL Server > Console User Guide 

## Database Instances

On Database Instances, you can create, modify, or delete database instances, or query status information of created database instances. 

### Creating Database Instances 

To crete a database instance, click [Create Database Instances] on top left of the list and go to page for database instance creation. Enter specifications, network, floating IP, database security group, and backup settings for the instance, click [Create Database Instances] and send a request for creation.   

![Create Database Instances 001](http://static.toastoven.net/prod_rds_mssql/db_instance_create_001.png)

* ❶ From Compute & Network, select a created VPC subnet. 
* ❷ When a database security group is not available, click [Create Database Security Groups] to immediately create and apply a security group. 
* For more details, see [Database Instances](./db-instance) and [Database Access](./database-connection).

With a database instance successfully created, you're automatically moved to the list of database instances. It takes a few minutes, or up to a few dozens of minutes, to create a database instance. 

### List of Database Instances

Brief information of database instances can be listed. 
One page shows up to 50 database instances on the list. 

![List of Database Instances 001](http://static.toastoven.net/prod_rds_mssql/db_instance_list_001.png)

* ❶ Search is available by the name or UUID of a database instance. 
* ❷ With a click on the condition, search results can be filtered by availability area or database instance status. 

![List of Database Instances > Conditions 001](http://static.toastoven.net/prod_rds_mssql/db_instance_list_cond_001.png)

* ❸ When selected, database instances may be enabled depending on the status. 
* ❹ Pagination is available when the current list is updated or if there are more than 50 database instances.
* ❺ Refers to the current CPU usage volume and the number of active sessions. 
* ❻ Refers to the status of database instance. Each status shows different value and color of status. 

### Modifying Database Instances

Available database instances can be easily modified in the setting via web console. 

![List of Database Instances 002](http://static.toastoven.net/prod_rds_mssql/db_instance_list_002.png)

* ❶ Select a database instance to modify from the list and click Modify on top right. 

After setting is changed, click [Modify] at the bottom of the page to modify database instance.  
Once request for modifying database instance is successfully made, you're moved to the list of database instances. It takes a few minutes, or up to a few dozens of minutes, to modify a database instance.  

![Modify Database Instances 001](http://static.toastoven.net/prod_rds_mssql/db_instance_modify_001.png)

* ❶ Unable to change the availability area. 
* ❷ With the change of database instance type, database shall restart.  
* ❸ Unable to change storage type. 
* ❹ Unable to reduce storage size, once it is increased. 
* ❺ Unable to change user ID.
* ❻ Without password, change is unavailable. 
* ❼ With the change of port, database shall restart. 
* ❽ Unable to change VPC. 

### Database Instance Details 

Select a database instance to show View Details at the bottom of page for detail information. 
The View Details panel is comprised of five tabs, providing more data related to each database instance. 

#### Basic Information 

You may check basic information of a selected database instance. 

![DB Instance Details > Basic Information 001](http://static.toastoven.net/prod_rds_mssql/db_instance_detail_inst_001.png)

* ❶ Click [Change] to change name of a database instance. 
* ❷ Click [Copy] to copy ID of database instance onto clipboard. 
* ❸ Shows IP information allowing the access to database instances. For a floating IP, another IP starting with 133 is exposed, and external access may be available depending on the database security group setting.   
* ❹ Check out the database security group which is now applied. Put a mouse cursor on the name of the security group and find out the rules of the group. 

#### Monitoring

Find out relevant indicators of a selected database instance on a chart. For more detail usage, see [Server Dashboard](./console-guide#_17). 

![Database Instance Details > Monitoring 001](http://static.toastoven.net/prod_rds_mssql/db_instance_detail_mon_001.png)

#### Events

Check out relevant events of a selected database instance. For more details, see [Events](./console-guide#_9).

![DB Instance Details > Events 001](http://static.toastoven.net/prod_rds_mssql/db_instance_detail_event_001.png)

#### Logs

Find out error logs of Microsoft SQL Server occurred at a selected database instance. 
Error logs are aligned in the latest time order, with 10 lines of logs on each page. 

![DB Instance Details > Logs 001](http://static.toastoven.net/prod_rds_mssql/db_instance_detail_log_001.png)

* ❶ Select a period to query. Without a period specified, the recent week's error logs show. 
* ❷ Initialize query period as default. 
* ❸ Pagination is available when the current list is updated or if there are more than 10 lines of error logs.

#### Backups

Check out the setting related to backup of a selected database instance and backup file information. 
One page shows up to 50 backups on the list. 

![DB Instance Details > Backups 001](http://static.toastoven.net/prod_rds_mssql/db_instance_detail_backup_001.png)

* ❶ Shows backup execution time. If time is not specified, time shows as the system defines. 
* ❷ Shows creation time of the most recently executed backup. 
* ❸ Search is available by the backup name. 
* ❹ Restore database instances by using selected backups. 
* ❺ Delete selected backups: only manual backups can be deleted.  
* ❻ Create manual backup files. 
* ❼ Pagination is available when the current list is updated or if there are more than 50 backup files. 

## Backups

On Backups, check out information on manual or auto backup files of all database instances. 

### List of Backups 

![List of Backups 001](http://static.toastoven.net/prod_rds_mssql/backup_list_001.png)

* ❶ Search is available by the backup name. 
* ❷ Restore database instances by using selected backups.
* ❸ Delete selected backups: only manual backups can be deleted. 
* ❹ Create manual backup files. 
* ❺ Pagination is available when the current list is updated or if there are more than 50 backup files. 

### Creating Backups

Click [Create Backups] on Backups and a popup shows to create a backup.
Select a database instance, enter name and click [Create] to execute backup.  

![List of Backups 002](http://static.toastoven.net/prod_rds_mssql/backup_list_002.png)

* ❶ Select a database instance to back up. Only currently available database instances show. 
* ❷ Enter name of a backup. 
* For more details, see [Backup and Restoration](./backup-restore).

## Restoration

RDS for SQL Server supports Restoration with Backup and Point-in-time Restoration.  
For more details, see [Backup and Restoration](./backup-restore).

### Restoration with Backup

You may restore data by using backup, from the Backup tab or the backup tab of View Database Details.  
Select a backup for restoration from the list, click [Restore], and it goes to the restoration page.  

![Restoration 001](http://static.toastoven.net/prod_rds_mssql/restore_001.png)
![Restoration 002](http://static.toastoven.net/prod_rds_mssql/restore_002.png)

Select type of a newly created database instance and set up, and press [Restore Database Instances] at the bottom to restore the database instance. 

![Restoration 003](http://static.toastoven.net/prod_rds_mssql/restore_003.png)

It takes a few minutes, or up to a few dozens of minutes, to restore a database instance.  

### Point-in-time Restoration

When the backup retention cycle is more than a day, database instances can be restored to a point in time during such retention period. 
Select a database instance to restore, click [Point-in-time Restoration] and it goes to the restoration page. 

![Restoration 004](http://static.toastoven.net/prod_rds_mssql/restore_004.png)

Provided on the same page for Restoration with Backup, you can select a time to restore on top of the page. 

![Restoration 005](http://static.toastoven.net/prod_rds_mssql/restore_005.png)

To restore to a different point in time other than recent available time, select [User Specified].

![Restoration 006](http://static.toastoven.net/prod_rds_mssql/restore_006.png)

Select type of a newly created database instance and set up, and press [Restore Database Instances]at the bottom to restore the database instance. It takes a few minutes, or up to a few dozens of minutes to restore a database instance. 

## Events 

On the Events tab, check out recent events or set up for event subscription. 
For more details on events and subscription, see [Monitoring](./monitoring#_2).

### List of Recent Events 

Check out events of recent occurrence. The 50 events that are exposed at one shot can be filtered out with many conditions.   

![List of Recent Events 001](http://static.toastoven.net/prod_rds_mssql/event_list_001.png)

* ❶ Select an event type to show. 
* ❷ Select a target to be searched with search words. Search is available with an event source or a message.  
* ❸ Select time of event occurrence. 
* ❹ With [Initialize], all search conditions are set as default. 
* ❺ Pagination is available when the current list is updated or if there are more than 50 events.

### Subscribing Events 

Click [Register Event Subscription] on top of the list of event subscription, and a popup shows to subscribe an events.
Enter information of an event to subsribe, click [Create] at the bottom and you're subscribed to the event.  

![Popup for Event Subscription 001](http://static.toastoven.net/prod_rds_mssql/event_subscription_001.png)

* ❶ Each event type can be subdivided into event codes and event sources.   
* ❷ Only project members are exposed on the list of users. Those whose names are authenticated only show their names and SMS, further on the page.  

![Popup for Event Subscription 002](http://static.toastoven.net/prod_rds_mssql/event_subscription_002.png)

* Select an event type and then choose an event code under. 

![Popup for Event Subscription 003](http://static.toastoven.net/prod_rds_mssql/event_subscription_003.png)

* ❶ Supports autocomplete. 
    * Available event codes are filtered for a keyword. 
    * Move up and down on your keyboard to select an event code, press Enter, and it is automataically completed. 
    * You may delete an event code, which has already been added, by pressing the backspace or clicking [x].
* ❷ You may select an event code with a click of the mouse. 

![Popup for Event Subscription 004](http://static.toastoven.net/prod_rds_mssql/event_subscription_004.png)

* Shows event sources for each event type. 
* ❶ Supports autocomplete. 
    * Available event sources are filtered for a keyword.
    * Move up and down on your keyboard to select an event source, press Enter, and it is automatically completed. 
    * You may delete an event source, which has already been added, by pressing the backspace or clicking [x].
* ❷ You may select an event source with a click of the mouse. 

## Parameter Groups

On Parameters, create a parameter group to be applied to a database instance, or modify parameters of a parameter group. 

### Creating Parameter Groups

To create a parameter group, default value must be copied from an existing parameter group. 
Select a target from the list of parameter groups, and click [Copy Parameter Groups].

![List of Parameter Groups 001](http://static.toastoven.net/prod_rds_mssql/parameter_group_list_001.png)

Enter name and description of a parameter group to newly create, click [Copy] to create a parameter group. 

![Copy Parameter Groups 001](http://static.toastoven.net/prod_rds_mssql/parameter_group_copy_001.png)

### Modifying Parameter Groups

Click name of a target to modify from the list of parameter groups, and it goes to parameter details. 

![List of Parameter Groups 002](http://static.toastoven.net/prod_rds_mssql/parameter_group_list_002.png)

Click [Edit Parameters] on top of the parameter details to enter into the edit mode. 

![Parameter Group Details 001](http://static.toastoven.net/prod_rds_mssql/parameter_group_detail_001.png)

Modify the parameter, click [Save Changes] to modify parameters of the parameter group. 

![Parameter Group Details 002](http://static.toastoven.net/prod_rds_mssql/parameter_group_detail_002.png)

* ❶ 키워드를 입력하여 노출되는 파라미터를 필터링할 수 있습니다.  
* ❷ 현재까지 수정된 모든 파라미터 변경사항이 취소하고 상세 화면으로 이동합니다.
* ❸ 변경 전과 후를 비교하여 보여주는 팝업이 노출됩니다.

![Parameter Group Details 파라미터 그룹 상세 003](http://static.toastoven.net/prod_rds_mssql/parameter_group_detail_003.png)

* ❹ 모든 파라미터의 값을 기본값으로 초기화합니다.
* ❺❻ 파라미터 수정 과정에서 발생한 에러메시지가 노출됩니다.

### 파라미터 그룹 비교 Comparing Parameter Groups

Compare two different parameter groups to find different parameters. 
Select two parameter groups to compare from the list.

![List of Parameter Groups 003](http://static.toastoven.net/prod_rds_mssql/parameter_group_list_003.png)

Click [Compare Parameter Groups] on top to check different parameters. 

![Compare Parameter Groups 001](http://static.toastoven.net/prod_rds_mssql/parameter_group_diff_001.png)

## Database Security Groups

From the Database Security Groups tab, database security group can be created or deleted. It is also possible to add, modify, or delete policy for each group.   
For more details on database security groups, see [Database Access](./database-connection).

### Creating Database Security Groups

On top of the list of dabase security groups, click [Create Database Security Groups], and a popup shows to create a database security group. 

![List of Database Security Groups 001](http://static.toastoven.net/prod_rds_mssql/db_security_group_list_001.png)
![Create Database Security Groups 001](http://static.toastoven.net/prod_rds_mssql/db_security_group_create_001.png)

* ❶ Click [+] to add security policy. 

Click [OK] at the bottom of the popup to create a database security group.  

### Modifying Database Security Groups

Select a database security group from the list, and click [Modify Database Security Groups] on top. 

![Modify Database Security Groups 001](http://static.toastoven.net/prod_rds_mssql/db_security_group_modify_001.png)

DB 보안 그룹의 이름과 설명을 수정할 수 있으며, 보안 정책은 별도로 수정해야 합니다.

### 보안 정책 수정 Modifying Security Policy 

DB 보안 그룹 목록에서 DB 보안 그룹을 선택하면 화면 하단에 보안 정책을 확인, 수정할 수 있는 상세 보기 패널이 노출됩니다.

![DB 보안 그룹 상세 001](http://static.toastoven.net/prod_rds_mssql/db_security_group_detail_001.png)

상세 보기 패널의 [보안 정책 생성] 버튼을 클릭하면, 보안 정책을 생성할 수 있는 팝업이 노출됩니다.

![DB 보안 그룹 상세 002](http://static.toastoven.net/prod_rds_mssql/db_security_group_detail_002.png)

상세 보기 패널에서 DB 보안 그룹 정책을 선택하면 정책을 변경, 삭제할 수 있습니다.

## Server Dashboard

서버 대시보드 탭에서는 DB 인스턴스의 각종 성능 지표를 차트 형태로 확인할 수 있습니다.
RDS for SQL Server 는 기본 시스템 지표 및 기본 SQL 서버 지표, 2개의 기본 레이아웃을 제공합니다.
기본 레이아웃은 삭제 및 변경이 불가능합니다.

![Server Dashboard 001](http://static.toastoven.net/prod_rds_mssql/server_dashboard_list_001.png)

* ❶ 생성된 DB 인스턴스가 목록에 노출됩니다. DB 인스턴스 선택 시, 연관된 차트를 확인할 수 있습니다.
* ❷ 레이아웃을 변경하여, 새로운 지표를 확인할 수 있습니다.
* ❸ 차트 조회 기간을 현재 시각 기준으로 설정합니다.

### How to Use User Layouts 

Click [Create Layout] to create a layout.  

![Server Dashboard 002](http://static.toastoven.net/prod_rds_mssql/server_dashboard_list_002.png)

![Server Dashboard 003](http://static.toastoven.net/prod_rds_mssql/server_dashboard_list_003.png)

You may add charts onto a new layout. 

![Server Dashboard 004](http://static.toastoven.net/prod_rds_mssql/server_dashboard_list_004.png)

Select a layout, click [Add Charts], and a popup shows to add more charts. 

![Server Dashboard 005](http://static.toastoven.net/prod_rds_mssql/server_dashboard_list_005.png)

With more charts added, you can find them on the layout. 

![Server Dashboard 006](http://static.toastoven.net/prod_rds_mssql/server_dashboard_list_006.png)

Charts on a user layout are free to be modified in the layout or size. 

![Server Dashboard 007](http://static.toastoven.net/prod_rds_mssql/server_dashboard_list_007.png)

* ❶ Area 1 can be re-located with a drag & drop. 
* ❷ To change the size, drag and drop the bottom right area.  
* ❸ Charts can be removed. 
