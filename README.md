DataStream README

Welcome to DataStream!

DataStream is designed to caputre recently changed oracle data in almost real time. The purpose is similar with Goldgate. 

DataStream 0.0.1 has been relased at 27/May/15.  

### Release note of v0.0.1.

##### Supports

* DataStream can parse archive log directly and store the changed PK into another database.  
* Data type char, varchar2, date, number as primary key are supported
* Mulit Instances for single source are supported.  Datastream is running with single thread in this release, so it has some performance issue.  Mining a 2G archive log needs 2 minutes, applying it needs 3 ~ 6 minutes. 

##### Limitations

* The table must has primary key.  The data type of primary key must be in [NUMBER, CHAR, VARCHAR2, DATE].  Or else Datastream will give warning and ignore this table. 
* Support common add/drop columns, but primary key definition change is not supported
* If Adding/Swaping/drop partition on a partitioned table, some data may be lost.  Mainly is because of DDL is not tracked.  see details 
* If the table have more than 250 columns, program will exit. If we run into this in real case, we will verify it more before using it. why
* Performance issue. Normally Single instance can handle 300+ tps, if we set the commit_logging to batch, the performance can increased by 1.5x. 

### Notes:
* This is an internal/dead project and we do not support it anymore
* Put it here just in case it may helpful for any people
