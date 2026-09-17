---
publish: true
draft: "true"
---
```dataview
TABLE WITHOUT ID 
    key AS "Missing File", 
    rows.file.link AS "Linked From"
FLATTEN file.outlinks AS out
WHERE !(out.file) AND !contains(meta(out).path, "/")
GROUP BY out
SORT length(rows) DESC, key ASC
```
