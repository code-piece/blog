---
title: "[Oracle] Converting a Non-Partitioned Table to a Partitioned Table"
date: 2022-03-20T23:19:04+07:00
draft: false
---

A non-partitioned table can be converted to a partitioned table with a <code>MODIFY</code> clause added to the <code>ALTER TABLE</code> SQL statement.

In addition, the keyword <code>ONLINE</code> can be specified, enabling concurrent DML operations while conversion in ongoing.

Conversion to a monthly range-partitioned table from today using the <code>ONLINE</code> keyword.

```SQL

ALTER TABLE table_name MODIFY
  PARTITION BY RANGE (date_column)
            INTERVAL (numtoyminterval(1,'MONTH')) 
	    (PARTITION table_name_p1 VALUES LESS THAN (TO_DATE('22-MAR-2022','DD-MON-YYYY'))) ONLINE;

```

