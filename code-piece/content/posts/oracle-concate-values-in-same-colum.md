---
title: "[Oracle] Concatenate values in same column"
date: 2022-03-22T13:31:20+07:00
draft: false
---

Concatenate values in same column with comma delimited. 

 - <b>Input</b>

   <table>
   <tr><th>column name</th></tr>
   <tr><td>Teemo</td></tr>
   <tr><td>Malphite</td></tr>
   <tr><td>Sona</td></tr>
   </table>

-  <b>Output</b>: <code>Teemo,Malphite,Sona</code>

```SQL

SELECT LISTAGG(column_name, ',') FROM table_name;

```



