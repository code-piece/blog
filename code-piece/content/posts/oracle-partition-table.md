---
title: "[Oracle] Partition Table"
date: 2022-03-12T00:26:30+07:00
draft: false
---
Create a monthly range-partitioned table starting from today.

```SQL
CREATE TABLE table_name
(
 ...
 date_column timestamp(6)
) PARTITION BY RANGE (date_column)
            INTERVAL (numtoyminterval(1,'MONTH')) 
	    (PARTITION table_name_p1 VALUES LESS THAN (TO_DATE('12-MAR-2022','DD-MON-YYYY')));

```

Additional: You need <code>numtodsinterval(1,'DAY')</code> if you want to partition by day.

