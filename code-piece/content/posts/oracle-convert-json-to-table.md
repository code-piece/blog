---
title: "Oracle convert json to table"
date: 2022-03-22T15:27:53+07:00
draft: false
---

 <b>Input:</b> 

```JSON
[
  {
    "id": 1,
    "name": "Lucian",
    "age": 18
  },
  {
    "id": 2,
    "name": "Caitlyn",
    "age": 25
  },
  {
    "id": 3,
    "name": "Soraka",
    "age": 28
  }
]

```
 <b>Output:</b>
 <table>
 <tr><th>ID</th><th>NAME</th><th>AGE</th></tr>
 <tr><td>1</td><td>Lucian</td><td>18</td></tr>
 <tr><td>2</td><td>Caitlyn</td><td>25</td></tr>
 <tr><td>3</td><td>Soraka</td><td>28</td></tr>
 </table>

 ```SQL
SELECT
    id,
    name,
    age
FROM
    JSON_TABLE ( '[{"id":1, "name":"Lucian","age":18},{"id":2,"name":"Caitlyn","age":25},{"id":3,"name":"Soraka", "age":28}]', '$[*]'
        COLUMNS (
            id NUMBER PATH '$.id',
            name VARCHAR2 ( 50 ) PATH '$.name',
            age NUMBER PATH '$.age'
        )
    );

 ```

