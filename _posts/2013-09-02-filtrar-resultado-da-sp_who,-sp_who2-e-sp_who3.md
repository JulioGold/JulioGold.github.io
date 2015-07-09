---
layout: post
comments: false
title: "Filtrar resultado da sp_who, sp_who2 e sp_who3"
excerpt: "Scripts para filtrar sp_who, sp_who2 e sp_who3"
date: 2013-09-02 10:07:00
mathjax: true
published: true
---

# Filtrar resultado da sp_who, sp_who2 e sp_who3

---

Segue scripts que possibilitam filtrar e manipular o resultado da sp_who, sp_who2 e sp_who3  

```sql
--------------------------------------

DECLARE @tmpWho TABLE
(
	spid        int
	,ecid       int
	,status     varchar(50)
	,loginame   varchar(255)
	,hostname   varchar(255)
	,blk        varchar(50)
	,dbname     varchar(255)
	,cmd        varchar(255)
	,request_id int
)

INSERT INTO @tmpWho EXEC sp_who

SELECT * FROM @tmpWho

--------------------------------------

DECLARE @tmpWho2 TABLE
(
	SPID         int
	,Status      varchar(50)
	,Login       varchar(255)
	,HostName    varchar(255)
	,BlkBy       varchar(50)
	,DBName      varchar(255)
	,Command     varchar(255)
	,CPUTime     int
	,DiskIO      int
	,LastBatch   varchar(255)
	,ProgramName varchar(255)
	,SPID2       int
	,REQUESTID   int
)

INSERT INTO @tmpWho2 EXEC sp_who2

SELECT * FROM @tmpWho2

--------------------------------------

DECLARE @tmpWho3 TABLE
(
	SPID           int
	,BlkBy         varchar(50)
	,Status        varchar(50)
	,Login         varchar(255)
	,loginfullname varchar(255)
	,HostName      varchar(255)
	,DBName        varchar(255)
	,Command       varchar(255)
	,CPUTime       int
	,DiskIO        int
	,LastBatch     varchar(255)
	,LastBatch2    varchar(255)
	,ProgramName   varchar(255)
	,SPID2         int
)

INSERT INTO @tmpWho3 EXEC sp_who3

SELECT * FROM @tmpWho3

--------------------------------------
```

abraço  