---
title: "[Oracle] Concatenate values in same column"
date: 2022-03-22T13:31:20+07:00
draft: false
---

Concatenate values in same column with comma delimited. 

 - Input
   name
   ----
   Teemo
   Malphite
   Sona

-  Output: Teemo,Malphite,Sona

```SQL

SELECT LISTAGG(column_name, ',') FROM table_name;

```


